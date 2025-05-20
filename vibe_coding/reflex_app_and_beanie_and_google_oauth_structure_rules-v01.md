# {{project-name}} AI 輔助程式設計規範

{{project-description}}

## 程式設計實務 (CODING_PRACTICES)

### 支援等級指南 (Guidelines for SUPPORT_LEVEL)

#### 專家級支援 (SUPPORT_EXPERT)

* 傾向於優雅、易於維護的解決方案，而非冗餘的程式碼。假設使用者已理解語言特性和設計模式。
* 在建議的程式碼中，應強調潛在的效能影響和最佳化機會。
* 將解決方案置於更廣泛的架構背景下進行闡述，並在適當時提出設計替代方案。
* 註解應專注於解釋「為何如此」（why），而非「做了什麼」（what）—— 良好的函式與變數命名應確保程式碼的可讀性。
* 無需提示，即應主動處理邊緣案例、競爭條件 (race conditions) 和安全性考量。
* 進行除錯時，應提供針對性的診斷方法，而非漫無目的的嘗試。
* 建議全面的測試策略，而不僅僅是範例測試，應包含模擬 (mocking)、測試組織和覆蓋率等考量。

### 文件撰寫指南 (Guidelines for DOCUMENTATION)

#### 文件更新 (DOC_UPDATES)

* 修改功能時，應更新 `/docs` 目錄下的相關文件。
* 保持 `README.md` 與新功能同步。
* 在 `CHANGELOG.md` 中維護變更日誌條目。

### 架構設計指南 (Guidelines for ARCHITECTURE)

#### 乾淨架構 (CLEAN_ARCHITECTURE)

* 嚴格將程式碼分層：實體 (entities)、使用案例 (use cases)、介面 (interfaces) 和框架 (frameworks)。
* 確保依賴關係指向內層，內層對外層無感知。
* 實作領域實體 (domain entities)，用於封裝 {{business_rules}}（業務規則），且不依賴於特定框架。
* 使用介面（端口，ports）和實作（適配器，adapters）來隔離外部依賴。
* 創建使用案例，用於協調針對特定業務操作的實體互動。
* 實作對應器 (mappers)，用於在不同層之間轉換資料，以維持關注點分離 (separation of concerns)。

## 網頁應用程式開發 (Web Application)

### Python 指南 (Guidelines for PYTHON)

#### Reflex 框架

* **狀態管理 (STATE_MANAGEMENT):** 在 `rx.State` 中使用具備類型提示的 `rx.Var` 來定義應用程式的 UI 相關狀態。
* **資料庫模型 (DATABASE_MODELS):**
    * 若使用 SQL 資料庫，建議使用 `rx.Model` (基於 SQLModel，整合 Pydantic 驗證) 來定義資料模型。
    * 若使用 MongoDB，應搭配 Beanie ODM。Beanie `Document` 模型本身已整合 Pydantic，用於資料驗證。
* **Beanie (MongoDB ODM) 整合:**
    * **生命週期管理 (LIFESPAN_MANAGEMENT):** `AsyncIOMotorClient` 的建立與關閉，以及 `beanie.init_beanie` 的呼叫，應透過定義一個 `asynccontextmanager` 並將其加入到 `rx.App` 實例的 `lifespan_tasks` 列表來進行管理。這確保資料庫連線在應用程式啟動時正確初始化，並在關閉時妥善釋放。 (詳細範例請參考「資料庫」->「NoSQL 指南」->「MongoDB」->「Beanie ODM 與 Async Motor 實踐指南」一節)。
    * **非同步操作 (ASYNC_OPERATIONS):** 所有在 `rx.State` 方法中與 Beanie 互動的資料庫操作，均須使用 `async/await` 語法。
* **業務邏輯封裝 (BUSINESS_LOGIC_ENCAPSULATION):** 將相關的業務邏輯和資料庫操作封裝在 `rx.State` 的方法中。透過繼承 `rx.State` 或組合子狀態 (substates) 的方式來組織和管理應用程式的服務及資源，以提升模組化、可測試性與資源管理效率。
* **非同步事件處理器 (ASYNC_EVENT_HANDLERS):** 對於涉及 I/O 的操作 (例如網路請求、檔案讀寫、資料庫查詢)，應優先使用 `async` 事件處理器 (event handlers) 以提升應用程式的反應速度和吞吐量，尤其是在處理 {{high_load_endpoints}}（高負載操作）時。
* **背景任務 (BACKGROUND_TASKS):** 對於不需要立即阻塞使用者介面回應的非關鍵性操作 (例如寄送郵件、資料清理)，應利用 Reflex 提供的 `@rx.background` 裝飾器將其作為背景任務執行。
* **例外處理 (EXCEPTION_HANDLING):** 在事件處理器 (`event handlers`) 和後端邏輯中，應使用標準的 Python `try-except` 機制進行周全的例外處理。針對 {{error_scenarios}}（特定錯誤情境），可考慮使用 `rx.window_alert`、`rx.toast` (例如整合 Radix Themes 的 Toast) 或自訂的 UI 組件向使用者提供清晰的錯誤反饋。
* **API 端點 (API_ENDPOINTS):** 主要透過將事件處理器 (event handlers) 綁定到 UI 組件的事件 (如 `on_click`, `on_submit`, `on_change` 等) 來驅動應用程式的邏輯和狀態更新。若需額外提供傳統的 HTTP API 端點 (例如供第三方服務呼叫)，可使用 `app.api_add_route()` 方法，並遵循 RESTful 原則設計路由及處理對應的 HTTP 方法。

#### 身分驗證與授權 (AUTHENTICATION_AUTHORIZATION)

##### 1. Google 身分驗證整合 (GOOGLE_AUTHENTICATION_INTEGRATION)

* **函式庫 (LIBRARY):** 應使用 `reflex-google-auth` 函式庫來整合 Google 身分驗證。
* **環境變數設定 (ENVIRONMENT_VARIABLES):**
    * `GOOGLE_CLIENT_ID`: (必要) 您的 Google OAuth 2.0 用戶端 ID。
    * `GOOGLE_CLIENT_SECRET`: (使用自訂登入按鈕或後端驗證授權碼時必要) 您的 Google OAuth 2.0 用戶端密鑰。
    * `GOOGLE_REDIRECT_URI`: (使用自訂登入按鈕或後端驗證授權碼時必要) 在 Google Cloud Console 中設定的已授權重新導向 URI。
    * 應在應用程式的設定檔 (如 `rxconfig.py` 使用 `os.environ.get`) 或部署環境中正確設定這些變數。
* **應用程式狀態整合 (`AuthState`):**
    * 建議創建一個繼承自 `reflex_google_auth.GoogleAuthState` 的基礎應用程式狀態類 (例如 `AuthState`)。
        ```python
        # 在 state.py 或 auth_state.py
        import reflex as rx
        from reflex_google_auth import GoogleAuthState
        from typing import List, Dict, Any
        from enum import Enum
        # 假設 User 模型和 UserGroup Enum 已定義 (見下文)
        # from .models import User, UserGroup

        class AuthState(GoogleAuthState):
            # 可在此處擴展，例如儲存應用程式特定的使用者資訊或群組
            # _current_user_app_groups: List[UserGroup] = [] # 範例

            @rx.event
            async def on_success(self, id_token: Dict[str, Any]):
                """
                在 Google 登入成功後觸發。
                """
                await super().on_success(id_token) # 呼叫父類別的 on_success 處理 token
                if self.token_is_valid:
                    # 首次登入處理：檢查使用者是否存在於應用程式資料庫，
                    # 若不存在則創建，並可賦予預設群組。
                    user_email = self.tokeninfo.get("email")
                    google_sub = self.tokeninfo.get("sub")
                    user_name = self.tokeninfo.get("name")

                    # --- 實際的資料庫操作 ---
                    # 例: existing_user = await User.find_one(User.google_sub == google_sub)
                    # if not existing_user:
                    #     new_user = User(
                    #         email=user_email,
                    #         fullname=user_name,
                    #         google_sub=google_sub,
                    #         groups=[UserGroup.VIEWER] # 預設群組
                    #     )
                    #     await new_user.insert()
                    #     self._current_user_app_groups = new_user.groups
                    # else:
                    #     self._current_user_app_groups = existing_user.groups
                    # --- 範例結束 ---
                    print(f"使用者 {user_name} ({user_email}) 登入成功。") # 應使用日誌系統
                else:
                    # self._current_user_app_groups = []
                    pass

            @rx.cached_var
            def current_user_groups(self) -> List['UserGroup']: # 請將 UserGroup 替換為實際的 Enum
                """
                獲取當前登入使用者的應用程式內部群組。
                此處為示意，實際應從資料庫或同步的 _current_user_app_groups 取得。
                """
                if not self.token_is_valid:
                    return []
                # --- 模擬從資料庫獲取 ---
                # user_email = self.tokeninfo.get("email")
                # if user_email and "admin" in user_email:
                #     return [UserGroup.ADMIN, UserGroup.AUTHENTICATED_USER]
                # elif user_email:
                #     return [UserGroup.VIEWER, UserGroup.AUTHENTICATED_USER]
                # --- 範例結束 ---
                return [] # 預設為空，應由 on_success 或其他邏輯填充

        # 應用程式的主 State 應繼承 AuthState
        # class AppState(AuthState):
        #     # ... 其他應用程式狀態 ...
        #     pass
        ```
    * 應用程式的主 `rx.State` (例如 `AppState`) 應繼承此 `AuthState`，以便在整個應用程式中存取驗證狀態和使用者資訊。
* **登入保護 (`require_google_login`):**
    * 使用 `reflex_google_auth.require_google_login` 裝飾器來保護需要登入才能存取的頁面或組件。
    * 此裝飾器會在使用者未登入時自動顯示 Google 登入按鈕。
        ```python
        # 在 pages.py 或 views.py
        # from .state import AuthState # 假設 AuthState 是您應用的主 State 或其基類
        # from reflex_google_auth import require_google_login

        # @rx.page(route="/protected_page")
        # @require_google_login
        # def protected_page() -> rx.Component:
        #     return rx.vstack(
        #         rx.text(f"歡迎, {AuthState.user_name}!"),
        #         rx.text("這是受保護的內容。")
        #     )
        ```
* **首次登入與使用者資料同步 (FIRST_LOGIN_USER_SYNC):**
    * 在 `AuthState` 的 `on_success` 事件處理器中，當使用者首次透過 Google 登入時，應檢查應用程式資料庫中是否已存在該使用者 (可使用 `tokeninfo['sub']` 作為唯一識別碼)。
    * 若使用者不存在，應在資料庫中創建新的使用者記錄，儲存必要的 Google 使用者資訊 (如 `sub`, `email`, `name`, `picture`)，並可指派預設的使用者群組。
    * 若使用者已存在，可更新其資訊 (如最後登入時間)。
    * `User` 模型 (例如在 MongoDB 中使用 Beanie) 應包含儲存 `google_sub` (唯一) 和 `groups` (群組列表) 的欄位。

##### 2. 角色型存取控制 (RBAC - ROLE_BASED_ACCESS_CONTROL)

* **群組定義 (`UserGroup` Enum):**
    * 使用 `enum.Enum` 定義應用程式中的所有使用者群組 (Roles)。
        ```python
        # 在 enums.py 或 models.py
        from enum import Enum

        class UserGroup(str, Enum):
            ADMIN = "系統管理員"
            EDITOR = "編輯者"
            VIEWER = "檢視者"
            AUTHENTICATED_USER = "已驗證使用者" # 代表任何已登入的使用者
            # ... 可依需求新增其他群組
        ```
* **使用者模型中的群組儲存 (USER_MODEL_GROUPS):**
    * 在應用程式的 `User` 資料庫模型中，應有一個欄位 (例如 `groups: List[UserGroup]`) 來儲存該使用者所屬的所有群組。
        ```python
        # 承接 MongoDB 指南中的 User 模型範例
        # from beanie import Document, Indexed
        # from typing import List, Optional
        # from pydantic import EmailStr
        # from .enums import UserGroup # 假設 UserGroup 在 enums.py

        # class User(Document):
        #     fullname: Optional[str] = None
        #     email: Indexed(EmailStr, unique=True)
        #     google_sub: Indexed(str, unique=True, sparse=True) # Google User ID, sparse 允許非 Google 用戶
        #     # hashed_password: Optional[str] = None # 若僅使用 Google 登入，此項可選
        #     groups: List[UserGroup] = []
        #     # ... 其他欄位

        #     class Settings:
        #         name = "users"
        ```
* **群組授權裝飾器 (`require_group`):**
    * **單一職責原則:** 應創建一個獨立的裝飾器 (例如 `require_group`) 來處理基於群組的授權，與 `require_google_login` (負責登入驗證) 分開。
    * `require_group` 裝飾器應在 `require_google_login` *之後* 套用，以確保在檢查群組前使用者已經登入。
    * 此裝飾器接收一個允許的群組列表 (`allowed_groups: List[UserGroup]`) 作為參數。
    * 它會檢查當前登入使用者的群組 (從 `AuthState.current_user_groups` 獲取) 是否至少有一個存在於 `allowed_groups` 中。
    * 若使用者不具備所需群組，則應顯示未授權的訊息或導向至特定頁面。

    * **`require_group` 裝飾器範例概念:**
        ```python
        # 在 decorators.py 或 auth_utils.py
        import reflex as rx
        import functools
        from typing import List, Callable, TypeVar
        # from ..state import AuthState # 假設 AuthState 是應用程式的 State
        # from ..enums import UserGroup # 假設 UserGroup Enum

        ComponentCallable = Callable[[], rx.Component]
        F = TypeVar('F', bound=ComponentCallable)

        def default_unauthorized_view_factory(
            required_groups: List[UserGroup],
            current_user_groups_var: rx.Var[List[UserGroup]] # 傳入 rx.Var
        ) -> rx.Component:
            """產生一個預設的未授權檢視元件。"""
            return rx.vstack(
                rx.heading("⛔ 存取權限不足", size="7", color_scheme="red"),
                rx.text("抱歉，您沒有足夠的權限來存取此頁面或功能。"),
                rx.text("所需群組：", font_weight="bold"),
                rx.hstack(
                    *[rx.badge(group.value, color_scheme="amber") for group in required_groups],
                    spacing="2"
                ),
                rx.text("您目前的群組：", font_weight="bold", margin_top="0.5em"),
                rx.cond(
                    rx.length(current_user_groups_var) > 0,
                    rx.hstack(
                        rx.foreach(
                            current_user_groups_var,
                            lambda group: rx.badge(group.value, color_scheme="grass")
                        ),
                        spacing="2"
                    ),
                    rx.text("(無群組或未載入)", color_scheme="gray")
                ),
                rx.link("返回首頁", href="/", margin_top="1.5em", color_scheme="blue"),
                align="center",
                spacing="3",
                padding="2em",
                border="1px solid #E2E8F0",
                border_radius="md",
                box_shadow="md",
                max_width="500px",
                margin="2em auto",
            )

        def require_group(
            allowed_groups: List[UserGroup],
            unauthorized_view_func: Callable[[List[UserGroup], rx.Var[List[UserGroup]]], rx.Component] | None = None
        ) -> Callable[[F], F]:
            """
            一個裝飾器，用於限制只有特定群組的使用者才能存取某個頁面或組件。
            應在 @require_google_login 之後使用。
            """
            actual_unauthorized_view_factory = unauthorized_view_func or default_unauthorized_view_factory

            def decorator(func_to_protect: F) -> F:
                @functools.wraps(func_to_protect)
                def wrapper(*args, **kwargs) -> rx.Component:
                    # 這裡的 AuthState 必須是當前頁面/組件上下文中的 State 實例。
                    # Reflex 的頁面和組件通常會自動處理 State 的上下文。
                    # 我們假設 AuthState.current_user_groups 是一個有效的 rx.Var[List[UserGroup]]。

                    # 創建一個 rx.Var[bool] 來表示是否有權限。
                    # 這需要在一個 State 類別中定義為 @rx.var。
                    # 為了通用性，我們創建一個臨時的內部組件和狀態來封裝這個邏輯。

                    class GroupPermissionCheckState(AuthState): # 繼承自應用的 AuthState
                        # allowed_groups_prop: rx.Var[List[UserGroup]] # 若要動態傳遞

                        @rx.var
                        def has_required_permission(self) -> bool:
                            # 確保已登入 (雖然外層的 require_google_login 應已處理)
                            if not self.token_is_valid:
                                return False
                            # 檢查群組
                            # print(f"權限檢查：使用者群組 {self.current_user_groups} vs 允許群組 {allowed_groups}")
                            return any(group in self.current_user_groups for group in allowed_groups)

                    return rx.cond(
                        GroupPermissionCheckState.is_hydrated, # 等待客戶端狀態就緒
                        rx.cond(
                            GroupPermissionCheckState.has_required_permission,
                            func_to_protect(*args, **kwargs), # 如果有權限，渲染原始組件
                            actual_unauthorized_view_factory(allowed_groups, GroupPermissionCheckState.current_user_groups)
                        ),
                        rx.center(rx.spinner(size="lg"), padding_y="5em") # 水合或檢查時的佔位符
                    )
                return wrapper # type: ignore
            return decorator # type: ignore
        ```
        **使用範例：**
        ```python
        # from .state import AuthState # 您的應用程式 AuthState
        # from .enums import UserGroup
        # from .decorators import require_group # 您定義的裝飾器
        # from reflex_google_auth import require_google_login

        # @rx.page(route="/admin_only")
        # @require_google_login # 1. 確保已登入
        # @require_group(allowed_groups=[UserGroup.ADMIN]) # 2. 檢查是否為管理員
        # def admin_only_page() -> rx.Component:
        #     return rx.vstack(
        #         rx.heading(f"管理員專區 - 歡迎 {AuthState.user_name}"),
        #         # ... 管理員內容 ...
        #     )

        # @rx.page(route="/editor_or_admin")
        # @require_google_login
        # @require_group(allowed_groups=[UserGroup.ADMIN, UserGroup.EDITOR])
        # def editor_or_admin_page() -> rx.Component:
        #     return rx.vstack(
        #         rx.heading(f"編輯區 - 使用者 {AuthState.user_name}"),
        #         # ... 編輯者或管理員內容 ...
        #     )
        ```
* **未授權處理 (UNAUTHORIZED_HANDLING):**
    * 當 `require_group` 檢查失敗時，應向使用者提供清晰的反饋。
    * 可以顯示一個標準的「未授權」組件（如 `default_unauthorized_view_factory` 所示），或導向到一個特定的未授權頁面。
    * 未授權組件應說明使用者為何無法存取，以及可能需要的權限。
* **群組管理 (GROUP_MANAGEMENT_INTERFACE):**
    * 雖然不直接是程式設計規範的一部分，但一個完整的 RBAC 系統通常需要一個管理介面，讓具備相應權限的使用者 (例如系統管理員) 能夠管理使用者及其所屬的群組。規範中可提及此需求。

##### 3. 安全性考量 (SECURITY_CONSIDERATIONS)

* **敏感資訊保護:** `GOOGLE_CLIENT_SECRET` 應被視為機密資訊，妥善保管，切勿直接寫在前端程式碼或版本控制系統中。應使用環境變數或安全的密鑰管理服務。
* **重新導向 URI 驗證:** 確保在 Google Cloud Console 中設定的「已授權 JavaScript 來源」和「已授權的重新導向 URI」是準確且限制性的，以防止釣魚攻擊和 token 洩漏。
* **ID Token 驗證:** `reflex-google-auth` 函式庫負責處理 Google ID Token 的驗證。確保使用的是最新版本的函式庫。
* **CSRF 與 XSS 防護:** Reflex 框架通常會提供 CSRF 保護機制。開發時應注意避免 XSS 漏洞，例如不要直接將未經處理的使用者輸入渲染為 HTML。

## 資料庫 (DATABASE)

### NoSQL 指南 (Guidelines for NOSQL)

#### MongoDB

##### Beanie ODM 與 Async Motor 實踐指南 (BEANIE_MOTOR_GUIDE)

* **初始化與生命週期管理 (INITIALIZATION_LIFESPAN_MANAGEMENT):**
    * Beanie 的初始化以及 `AsyncIOMotorClient` 的連線管理，應透過定義一個非同步上下文管理器 (`@asynccontextmanager`) 並將其加入 Reflex 應用程式的 `lifespan_tasks` 清單來實現。這種方式可以更優雅地管理資源的設定與清理。
    * `asynccontextmanager` 應包含 `AsyncIOMotorClient` 實例的建立、`beanie.init_beanie` 的呼叫，以及在 `finally` 區塊中關閉 `AsyncIOMotorClient` 實例。
    * 範例 (通常在專案的 `rxconfig.py` 或主應用程式設定檔中):
        ```python
        # rxconfig.py 或您的主應用程式設定檔
        import reflex as rx
        import motor.motor_asyncio
        from beanie import init_beanie
        from contextlib import asynccontextmanager
        from typing import AsyncIterator, Any # AsyncIterator 用於 asynccontextmanager

        # 假設您的 Beanie Document 模型定義在 your_app.models 模組
        # 例如: from your_app.models import User, Item 
        # 以及與身分驗證相關的 User 模型
        # from your_app.models import User # (包含 google_sub, groups 等欄位)

        motor_client: motor.motor_asyncio.AsyncIOMotorClient | None = None

        @asynccontextmanager
        async def mongodb_lifespan_manager(app: rx.App) -> AsyncIterator[None]:
            global motor_client
            db_connection_string = "mongodb://localhost:27017" # 範例，應從設定讀取
            db_name = "mydatabase" # 您的資料庫名稱

            print(f"正在連線至 MongoDB ({db_name})...")
            motor_client = motor.motor_asyncio.AsyncIOMotorClient(db_connection_string)
            
            try:
                await init_beanie(
                    database=motor_client[db_name],
                    document_models=[
                        "your_app.models.User",  # 包含身分驗證相關欄位的 User 模型
                        "your_app.models.Product", 
                        # 列出所有其他的 Beanie Document 模型路徑
                    ]
                )
                print(f"已連線至 MongoDB ({db_name}) 並初始化 Beanie。")
                yield # 應用程式運行階段
            finally:
                if motor_client:
                    motor_client.close()
                    print("已關閉 MongoDB 連線。")
                motor_client = None
        ```
    * **重要提示**:
        * 使用 `@asynccontextmanager` 可以確保資源（如資料庫連線）在應用程式啟動時被正確設定，並在應用程式結束時（即使發生錯誤）被妥善清理。
        * `yield` 語句之前的部分會在應用程式啟動時執行，之後的部分 (通常在 `finally` 區塊中) 會在應用程式關閉時執行。
        * 在 `init_beanie` 的 `document_models` 參數中，使用模型的完整字串路徑 (例如 `"your_app.models.User"`) 是推薦的做法，以避免循環匯入問題。

* **模型定義 (MODEL_DEFINITION):**
    * 所有 MongoDB 的文件模型均須繼承 `beanie.Document`。
    * 利用 Pydantic 的特性進行嚴謹的類型提示 (type hints) 與資料驗證 (validation)。
    * 應在模型內部使用 `Settings` 內部類別來配置集合名稱 (collection name) 或其他 Beanie 特定設定。
    * **User 模型範例 (整合身分驗證需求):**
        ```python
        # your_app/models.py
        from typing import Optional, List
        from pydantic import BaseModel, EmailStr, Field
        from beanie import Document, Indexed
        from enum import Enum # 用於 UserGroup

        # 假設 UserGroup Enum 定義在此或已匯入
        class UserGroup(str, Enum):
            ADMIN = "系統管理員"
            EDITOR = "編輯者"
            VIEWER = "檢視者"
            AUTHENTICATED_USER = "已驗證使用者"

        class Address(BaseModel):
            street: str
            city: str
            zip_code: str

        class User(Document):
            fullname: Optional[str] = None
            email: Indexed(EmailStr, unique=True) # Google Email
            google_sub: Indexed(str, unique=True, sparse=True) # Google User ID, sparse 允許未來支援非 Google 登入
            # hashed_password: Optional[str] = None # 如果僅用 Google 登入，此欄位可選或移除
            age: Optional[int] = Field(None, gt=0)
            addresses: List[Address] = []
            groups: List[UserGroup] = Field(default_factory=lambda: [UserGroup.VIEWER]) # 新使用者預設群組

            class Settings:
                name = "users" # 明確指定集合名稱
        ```

* **非同步操作 (ASYNC_OPERATIONS):**
    * 所有使用 Beanie 進行的資料庫互動都必須採用 `async/await` 語法。

* **查詢與檢索 (QUERYING_RETRIEVAL):**
    * 優先使用 Beanie 提供的查詢 API。
    * 善用 Beanie 內建的查詢運算子。
    * 使用 `.project()` 方法來指定查詢時僅返回需要的欄位。

* **資料建立與更新 (DATA_CREATION_UPDATE):**
    * 使用 `.insert()`, `.replace()`, `.save()`, `.update()` 等方法。
    * **使用者創建範例 (在 `AuthState.on_success` 中):**
        ```python
        # # (部分程式碼，展示如何在 on_success 中創建 User)
        # from .models import User, UserGroup # 假設模型和 Enum 已定義
        # # ...
        # async def on_success(self, id_token: dict):
        #     await super().on_success(id_token)
        #     if self.token_is_valid:
        #         user_email = self.tokeninfo.get("email")
        #         google_sub = self.tokeninfo.get("sub")
        #         user_name = self.tokeninfo.get("name")
        #
        #         if google_sub: # 確保 google_sub 存在
        #             existing_user = await User.find_one(User.google_sub == google_sub)
        #             if not existing_user:
        #                 new_user = User(
        #                     fullname=user_name,
        #                     email=user_email,
        #                     google_sub=google_sub,
        #                     groups=[UserGroup.VIEWER] # 新使用者的預設群組
        #                 )
        #                 await new_user.insert()
        #                 print(f"新使用者 {user_name} 已創建。")
        #             else:
        #                 # 可選擇更新現有使用者資訊，例如 fullname 或最後登入時間
        #                 # await existing_user.update(Set({User.fullname: user_name}))
        #                 print(f"使用者 {existing_user.fullname} 已存在。")
        # # ...
        ```

* **資料刪除 (DATA_DELETION):**
    * 使用 `.delete()` 方法。

* **聚合框架 (AGGREGATION_FRAMEWORK):**
    * 使用 `.aggregate()` 方法執行 MongoDB 的聚合管道操作。

* **索引管理 (INDEXING):**
    * 透過在 `beanie.Document` 模型的欄位上使用 `Indexed()` 來聲明索引。
    * `User` 模型中的 `email` 和 `google_sub` 欄位應建立唯一索引。

* **結構驗證 (SCHEMA_VALIDATION):**
    * Beanie 強制使用 Pydantic 模型，確保資料寫入前的驗證。

* **關聯與嵌入 (RELATIONSHIPS_EMBEDDING):**
    * 根據資料存取模式合理選擇使用嵌入式文件或引用。

* **效能考量 (PERFORMANCE_CONSIDERATIONS):**
    * 正確使用索引和投影，考慮批次操作。

---

> References
>
> Powered by: Gemini 2.5pro
>
> Cited from: [@przeprogramowani](https://10xrules.ai/)

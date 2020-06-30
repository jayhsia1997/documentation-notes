
- 自己製作出可以讓別人接我們的 OAuth2 的服務 (自己即是 Provider)
- Oauth 引入 authorization layer 來把 Resource Owner && Client 分開
    - 用以解決 Server 與 第三方服務 之間的權限問題
- 在 Oauth 中, Client 向 Resource Owner 索取 存取權(取得 credentials) 來存取 Resource Owner 上的資源(在 Resource Server 上).
- Client 出示 Authorization Grant 來認證自己, Authorization Server 才會頒發 Access Token 給 Client, 用此來存取 Resource Server 上的 Protected Resources (而非使用 Resource Owner 的帳密 來做資源請求)
    - Access Token 記載了 Period && Scope
- Client 取得來自 Resource Owner 的 Authorization Grant. 此類型有 4 種(但可擴充), 至於用哪種類型, 要看 Client 請求授權的方法 or Authorization Server 支援的類型來決定.
    - 
- Client 拿 Authorization Server 頒發的 Access Token 去 Resource Server 請求 Protected Resource, Resource Server 驗證 Access Token, 若合法, 則回覆請求.
- Access Token 可以加上用來取得授權資訊的 identifier (ex: 編號 or 識別字) or 內建可以驗證的授權資訊(ex: 數位簽章)
- Authorization Grant type 區分為 4 種:
    - Authorization Code Grant Type Flow
        - 向 Authorization Server 先後分別取得 Grant Code && Access Token
        - 適合 Confidential Clients (ex: Server 上的 App)
        - 可核發 Refresh Token
        - 需要 User-Agent Redirection
    - Implicit Grant Type Flow
    - Resource Owner Password Credentials Grant Type Flow
    - Client Credentials Grant Type Flow
- Clients 類型分為 Public && Confidential 兩種
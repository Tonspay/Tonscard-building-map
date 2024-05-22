# MPC Wallet building draft

Tonscard require to generate MPC wallet for every users by using [lit-protocol](https://www.litprotocol.com/) service . Every user will generate a wallet which auth by Telegram Oauth & Telegram Webapp-sign-data .

MPC Wallet is a standalong services , including :

- **Auth router back-end**
    - Stacks : 
        - Node.js
        - Rust (later)
    - Functions :
        - Accept Telegram Oauth and send to web3auth/other MPC provider
        - Accept Telegram webapp login sign.
    
-  **Webapp font-end**
    - Stacks :
        - React-js
    - Page with functions :
        - Auto login with keypair back by redirect

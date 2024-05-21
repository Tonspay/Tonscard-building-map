# Tonscard dev logic map

Tonscard service work base on the support of Visa/Master crypto card channel support . Every user have it's own hot-wallet for crypto deposite . But the major service support asserts & chains including : 

- TRON-USDT
- ARB-USDT
- ETH-USDT

Which means a lot limit including chains support & asserts support . The way to sloved is add the crosschain support inside the font-end of tonscard service . And to extend the finance functions of Tonscard service , we have to build some aggregator on different chains to allows users to use .

## Main parts of Tonscard

- Visa/Master Hot Wallet
    - Every users have a directly Visa/Master hot wallet for the Visa/Master card purchas . 
    - Accept USDT in TRON/ARB/ETH only
- Users telegram base MPC wallet(standalong)
    - Every users should have a MPC wallet for mulity chains using telegram Oauth 
    - All the asserts of users set in MPC wallets for mulity chains including :
        - TON 
        - Solana
        - Arbitrum
        - BSC
    - Allows users to :
        - Export privateKey
        - Transfer
        - Farmining(staking) / Lending (into hot-wallet )
- One tap crosschain service . bridge aggregator .
    - By add crosschain support with bridge aggregator
    - Single Dapp font-end . ( As a standalong Dapp )
    - Inner MPC support font-end (For Tonscard users)
- Farmining aggregator (standalong)
    - Support mulity chains aggregator for staking protocols & farmining protocols 
    - Single Dapp font-end . ( As a standalong Dapp )
    - Inner MPC support font-end (For Tonscard users)
- Lending aggregator (standalong)
    - Support mulity chains aggregator for Lending protocols , including Token lending & NFT lending
    - Single Dapp font-end . ( As a standalong Dapp )
    - Inner MPC support font-end (For Tonscard users)

## Building plan

The tonscard service is now splited into 5 different parts .

As for the developing of tonscard service , including :

- ### Tonscard bot & webapp & browser-app
    #### Main part of Tonscard user system . including **functions** : 
    - User system ( base on telegram Oauth )
    - Crypto asserts balance management (Mixed hot-wallet & MPC wallets)
        - Fiat accept wallet ( hot-wallet )
        - Decentraliezed wallet ( MPC wallet )
    - Auto asserts bridge (digest into Visa accept crypto);
    - MPC wallet default farmining entrance
    - MPC wallet lending entrance
    
    #### During the developing it can splited into parts : 
    - **Service back-end**
        - Stacks : 
            - Node.js
            - Rust (later)
        - Restful-api functions :
            - User system base on telegram Oauth
            - Hot wallet control
            - Card balance control
    
    -  **Webapp font-end**
        - Stacks :
            - React-js
        - Page with functions :
            - User profile
            - Hot-wallet control
            - MPC wallet control
            - Auto farmining & stable-coin control
            - Lending aggregator
    
    - **Telegram bot back-end**
        - Stacks : 
            - Node.js
            - Golang (later)
        - Major functions
            - Menu and router for Webapp

- ### Tonscard MPC wallet service . Telegram webapp
    Tonscard MPC wallet work as a standalong service with absctruct account support .
    #### Main functions of MPC wallet
    - Oauth using Telegram
    - Auth by telegram web-app login
    
    #### During the developing it can splited into parts : 
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

- ### Tonscard one tap crosschain bridge aggregator 
    Tonscard crosschain service including a standalong protocol & font-end .

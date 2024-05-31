# Bridge aggrator building draft

Tonscard require to have a bridge aggrator for TON chain to help user auto crosschain into Visa/Master hotwallet support chain/asserts .

TON chain have an official [bridge](https://bridge.ton.org/) . which not working very well and have less chains support . So we have to build and bridge aggrator base on 3th part bridges including layer0 & CCTP . 

Bridge aggrator is a standalong services , including :

- **Bridge router back-end**
    - Stacks : 
        - Node.js
        - Rust (later)
    - Functions :
        - Find best price during bridges supports
    
-  **Webapp font-end**
    - Stacks :
        - React-js
    - Page with functions :
        - Connect wallet
        - Call back-end for best bridge router path
        - Wallet call up to pay the crosschain exchange 

The bridge is not only about the TON chain . It should support different chains including SOL/ARB/BSC/POLYGON/TRON .

To achive the functions of bridge aggrator . we will use customer bridges including :

- TON-Bridge
- ff.io
- simple-swap


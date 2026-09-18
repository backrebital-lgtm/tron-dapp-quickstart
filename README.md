# TRON DApp Quickstart

A modern **TRON DApp starter template** that helps developers quickly build decentralized applications on the **TRON blockchain**.  
It demonstrates **wallet integration**, **sending transactions**, and **interacting with smart contracts** — core features most TRON DApps require.

Any questions, feedback or feature requests are welcome [here](https://github.com/tronweb3/tron-dapp-quickstart/issues/new).

---

## Tech Stack

- **TronWeb** – TRON blockchain SDK
- - **TronWalletAdapter** – Wallet connection & signing
  - - **React 19 + TypeScript 5.8.3** – Frontend framework
    - - **Vite 7.1.2** – Fast build tool
     
      - ---

      ## Quick Start

      ```bash
      # 1. Clone this repo
      git clone https://github.com/tronweb3/tron-dapp-quickstart.git

      # 2. Install dependencies
      npm install

      # 3. Start dev server
      npm run dev
      ```

      Environment requirements:

      - Node.js 22+
      - - npm 10.5.0+
       
        - The included `.env` targets the Nile Testnet. For local overrides, use `.env.local` and keep API keys or other secrets out of committed files.          # Utility functions
        - │   ├── App.tsx        # App root (providers + router)
        - │   ├── constants.ts   # Constants
        - │   ├── locale         # i18n resources
        - │   └── main.tsx       # Entry file
        - ├── .env               # Environment variables
        - ├── index.html
        - ├── tsconfig.json
        - └── vite.config.ts
        - ```

          **Focus on the `src/` folder** when developing — add new pages, components, hooks, or utilities here.

          ---

          ## Core Features

          ### 1. Wallet Integration

          - Built-in TRON wallet connection with `TronWalletAdapter`
          - The `Connect Wallet` button is implemented in [`WalletActionButton`](src/components/WalletActionButton/WalletActionButton.tsx); connect before submitting a transfer
          - Secure signing of transactions
          - Docs: [TronWalletAdapter](https://walletadapter.org/)

          ---

          ### 2. Transaction Templates

          #### a) Sending TRXThe example passes the amount to `tronWeb.transactionBuilder.sendTrx`. TronWeb supports **36 transaction types**; replace the transaction in Step 3 to send other types.

          #### b) TRC20 Token Transfer

          File: [`TransferTRC20.tsx`](src/components/Transfer/components/TransferTRC20.tsx)

          - Uses `tronWeb.transactionBuilder.triggerSmartContract`
          - Example of interacting with TRC20 smart contracts

          #### c) Delegate Workflow

          File: `src/components/Delegate/Delegate.tsx`

          Covers:

          - Fetch account info (`tronWeb.trx.getBalance`)
          - Query and show delegation details
          - Send `freezeBalanceV2` + `delegateResource` transactions

          ---

          ### 3. Environment Config

          - Managed via **Vite `.env` file**
          - Default prefix: `TDQ_`
          - The sample `TDQ_NILE_TEST_NET` value is `https://nile.trongrid.io`
          - Docs: [Vite env config](https://vite.dev/guide/env-and-mode)

          ---

          ### 4. Theme Switch (Light/Dark)

          - Located in `src/components/ThemeSwitch/ThemeSwitch.tsx`
          - Prevents flickering by setting `data-theme` early in entry file (`main.tsx`)
          - To disable: remove initialization in `main.tsx` + remove component in `Header.tsx`

          ---

          ### 5. Localization (i18n)

          - Powered by **i18next**
          - Language definitions in `src/locale`

          Add a new language:

          1. Add locale file in `src/locale`
          2. Configure in `useLocale.ts`
          3. Import Antd locale in `App.tsx`
          4. Update each language object with new language code

          Remove i18n:

          - Delete `src/components/LocaleDropdown`, `src/locale` and `src/hooks/useLocale.ts`
          - Remove related imports

          ## License

          This project is licensed under the [MIT License](./LICENSE).
          

          File: [`TransferTRX.tsx`](src/components/Transfer/components/TransferTRX.tsx)

          Steps:

          1. Connect a wallet and enter the recipient address
          2. Enter the amount in SUN (1 TRX = 1,000,000 SUN)
          3. Build the TRX transfer with TronWeb
          4. Sign the transaction through `TronWalletAdapter`
          5. Broadcast the signed transaction to the TRON blockchain

          
       
        - ---

        ## Project Structure

        ```
        tron-dapp-quickstart
        ├── src
        │   ├── assets         # Static assets (images, etc.)
        │   ├── components     # Reusable UI components
        │   ├── hooks          # Custom React hooks
        │   ├── pages          # Page-level components
        │   ├── router         # Route configuration
        │   ├── utils          # Utility functions
        

## How to Build your First dApp on the Decentralized Data Cloud?
**Get started** building your decentralized data dApps!

### Setting up your wallet (5 minutes)

1. [Create and top up your Cere Wallet](https://github.com/Cerebellum-Network/grant-program/blob/master/documentation/GETSTARTED.md#how-to-create-and-top-up-your-cere-wallet)
2. [Top up DDC account](https://github.com/Cerebellum-Network/grant-program/blob/master/documentation/GETSTARTED.md#how-to-top-up-ddc-account)
3. [Export your Cere Wallet as JSON.](https://github.com/Cerebellum-Network/grant-program/blob/master/documentation/GETSTARTED.md#export-your-cere-wallet-as-json)


## Code examples

### ⚠️Before you start ⚠️

1. Always check if an example is using TESTNET or MAINNET
2. Always check if the wallet you are using is TESTNET or MAINNET (by default it’s mainnet)


**Testnet details**

- Developer console: https://stage.developer.console.cere.network/
- Cere wallet: https://wallet.stg.cere.io/wallet/home
- CDN: https://cdn.testnet.cere.network/
- Cluster id - 0x825c4b2352850de9986d9d28568db6f0c023a1e3Mainnet

**Mainnet details**

- Developer console: https://developer.console.cere.network/
- Cere wallet: https://wallet.cere.io/
- CDN: https://cdn.dragon.cere.network/
- Cluster id: 0x0059f5ada35eee46802d80750d5ca4a490640511

### Pre-requisites

- How to use your exported Cere Wallet (JSON):
  https://github.com/Cerebellum-Network/cere-ddc-sdk-js/blob/main/examples/node/5-use-exported-account/index.ts
- How to index files so they are visible in the Developer console:
  https://github.com/Cerebellum-Network/cere-ddc-sdk-js/blob/main/examples/node/6-developer-console-compatibility/index.ts

### Basics


- Create a bucket: https://github.com/Cerebellum-Network/cere-ddc-sdk-js/blob/main/examples/node/2-store-read-file/index.ts
- Store & read files: https://github.com/Cerebellum-Network/cere-ddc-sdk-js/blob/main/examples/node/2-store-read-file/index.ts
- Upload a website: https://github.com/Cerebellum-Network/cere-ddc-sdk-js/tree/main/examples/node/3-upload-website
- Store & read events: https://github.com/Cerebellum-Network/cere-ddc-sdk-js/tree/main/examples/node/4-store-read-events

### End-to-end

- Telegram Mini App that enables token-based subscriptions to gated video content
    - Back-end: https://github.com/cere-io/integration-telegram-app-bot
    - Front-end: https://github.com/cere-io/integration-telegram-app
    - End-to-end demo:

      [tgbot.mp4](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/0528d914-151f-4afc-86a6-dab55e5f056e/tgbot.mp4?table=block&id=137d8000-83d6-80db-8c32-f021daa357bd&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=u5wbWIU6vz32ex1FtoLWg8AVGW5-A2EjNcDyB0B4hUM&downloadName=tgbot.mp4)

- Serverless, decentralized image conversion
    - Acurast compute example: https://github.com/Acurast/acurast-example-apps/blob/main/apps/app-heic-to-png/src/index.ts

## Docs

- Developer Console: https://developer.console.cere.network/
- Developer hub:  https://www.developer.cere.network/get-started
- Cere Wallet:  https://wallet.cere.io/
- Knowledgebase: https://www.cere.network/hub
- DDC SDK: https://docs.cere.network/ddc/sdk
- DDC SDK Github: https://github.com/Cerebellum-Network/cere-ddc-sdk-js
- DDC SDK Examples: https://github.com/Cerebellum-Network/cere-ddc-sdk-js/tree/main/examples
- Cere Network Github: https://github.com/Cerebellum-Network


#### How to create and top up your Cere Wallet?

1. Open [Developer Testnet Console](https://stage.developer.console.cere.network/) application

   ![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/94b14eb1-f00b-4bb6-bab2-52c293da6230/image.png?table=block&id=339b011e-3747-44db-8344-0c8a182dd61f&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=X8pg4sZGKTla8ZDpXxP0ddiuksafsBBILJ1m8hLRONg&downloadName=image.png)

2. Create a new account
3. At the left corner open violet Cere wallet widget and click on “Open wallet” button

![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/e5fa187c-f427-43f2-a664-23747e78e204/image.png?table=block&id=08f6d956-9781-48d4-82f5-f14ad8dbc46e&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=X7Vkw2zwVQSrIrUVlhjvZqLlbzAxrN40wcAyJXH-vTI&downloadName=image.png)

4. Here are wallet public keys for different networks. Use them to receive Cere tokens.

![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/aa3c36f2-0675-4c95-a749-3b7e51d75dd0/image.png?table=block&id=138d8000-83d6-80bd-89f3-e508078848e8&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=HUJ7WzTT0Fv_H-RE-oRCvjcM4UVKgOvXLdbUWs_oPc4&downloadName=image.png)

5. On the “Content Storage” page click on “Join Cere Discord” button and join [Cere Network channel](https://discord.com/invite/8RBXaQ6nT5).

![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/c30f84dd-44a1-4d5f-8506-de14664d6139/image.png?table=block&id=65f008e5-3040-43a6-b788-0b81c988b619&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=mXre1vHzQOelH6TfNghTjqCe08lrOI9SjumKTIlww2M&downloadName=image.png)

Once you have your Cere Wallet and DDC account set up, you have to export your account as JSON file in order to use it in your code-base .

6. Request Cere tokens in the channel using Cere Wallet public key (address that starts with a 6). InvB  will respond as soon as possible but they are working on EU hours.

#### How to top up DDC account?

1. Open [Developer Testnet Console](https://stage.developer.console.cere.network/login) application and click on Account menu at the right corner
2. Then click on “Top up” button

![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/681b45a9-20f0-4d62-820e-a71722544651/image.png?table=block&id=15ce5086-650d-4a59-825f-47342e0f5c7d&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=KzyOjWj7Ixzzodg8Bu7bzGDlBlizaFIc22rnXAa3rxM&downloadName=image.png)

3. On [the “Top up your account” page](https://stage.developer.console.cere.network/top-up) enter any valid amount of Cere tokens  and click on “Confirm button”

⚠️ **If you have 50 $CERE top up 45; don’t top up all! You need $CERE to pay for gas** ⚠️

![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/fc03dced-f624-4099-a333-0a89cbe9a830/image.png?table=block&id=c2df23ef-a9b5-4920-8c42-3f5323b893bb&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=3mMitqotb7z64P_X4PmUv6Zy_xj99V0d_Leomv7d6n0&downloadName=image.png)

4. Wait ~30 seconds. If transfer was successful you will see “Congrats!” message. If you will see an error message, then contact us in Discord [Cere Network channel](https://discord.com/invite/8RBXaQ6nT5).

![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/587b957d-25e1-45bc-8951-47fbe6830f27/image.png?table=block&id=c67e2ba4-30ad-4eee-895a-7795f52ad588&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=-hwtDYNi0IhQ6GzXppVix4I8o9NOzRIo9f-cHlH3vDA&downloadName=image.png)

5. Now you can go to [the “Content Storage” page](https://stage.developer.console.cere.network/content-storage) and upload files to the buckets!



Once you have your Cere Wallet and DDC account set up, you have to export your account as JSON file in order to use it in your code-base .

#### Export your Cere Wallet as JSON

Once you have your Cere Wallet, you have to export it and download a JSON file to handle authentication in your code base. This only takes 3 minutes:

1. Go to https://wallet.cere.io/
2. Log in with the same account you created for the Developer Console

   ![{6BB456C0-42B3-41D8-8F3A-1FBAB5AD0AA9}.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/f798b352-c618-4337-a690-34c97c088124/6BB456C0-42B3-41D8-8F3A-1FBAB5AD0AA9.png?table=block&id=137d8000-83d6-80bc-9f5f-dc31e10693e8&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=lNHQV_IBVY2qIAqHDjm3ChhS3aKV63acvEjx3irIdYU&downloadName=%7B6BB456C0-42B3-41D8-8F3A-1FBAB5AD0AA9%7D.png)

3. Click on “Settings” at the top of the wallet

   ![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/9520ae4a-ba1f-47b7-8664-33d022e8bf31/image.png?table=block&id=137d8000-83d6-80ba-a9aa-cff6159257a2&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=vbyg3KHibOGCYt2Kp3HSjarwMYwJAUb_dflQWLvLdb4&downloadName=image.png)

4. Next fill in a password to encrypt your file. This is ANYTHING you want eg. “1234_IS_not_safe”

   ![image.png](https://file.notion.so/f/f/2ca1d50f-3068-4ab0-bb41-0e822d81461f/8107d77d-fb42-4d5a-8696-50a75d464a60/image.png?table=block&id=137d8000-83d6-80f4-8910-daff17beee6c&spaceId=2ca1d50f-3068-4ab0-bb41-0e822d81461f&expirationTimestamp=1743616800000&signature=OwmBxiYT_xAqixa4H9xvRlegGkM7YKE68O5Z399rxX4&downloadName=image.png)

5. Next click “export account” to download your JSON file

You are good to go 🚀🚀🚀 Now check [this code example](https://github.com/Cerebellum-Network/cere-ddc-sdk-js/blob/main/examples/node/5-use-exported-account/index.ts) on how to authenticate using the JSON.

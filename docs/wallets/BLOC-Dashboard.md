# **What is the BLOC Dashboard ?**

The official BLOC.MONEY [(BLOC) Dashboard](https://dashboard.bloc.money) makes cryptocurrency accessible by anyone in the world regardless of their geographic location or status and gives access to financial services with respect of user privacy. Create your wallet to receive and send BLOC, discover a new disruptive ecosystem and get involved with the community.

Cryptocurrency for everyone made it easy, safe and private. 

## **Features**

Send and receive BLOC at the touch of a button, anytime, anywhere and to anyone.
Backup and recover your wallet on any device with the recovery keys by the app.
Even if you loose your phone you will not lose your BLOC.
Pay and get Paid using the QR code feature without having to know the recipient BLOC address
Receive notifcations for transactions
Use the BLOC Widget to get real time informations about BLOC
Join the BLOC community on the private chat room

Spin and roll the BLOC coin in augmented reality including 3 different colors and 2 animation with sound (require iOS 12)

They aren't any hidden servers to backup or store your coins, you are in control 100%
A simplified codebase makes BLOC Dashboard quick, lightweight and responsive
Connect directly to the BLOC network without having the need to download the full blockchain on your phone

## **BLOC world at your fingertips**

By registering an account on the BLOC dashboard you will have access to the following services:

- Complete informations about the BLOC network in one simple and clean view
- Create a BLOC wallet
- Send / Receive BLOC
- Transactions list
- Address Book
- Built-in block explorer
- Charts with market cap, trading volume and price
- Latest news from the BLOC
- Videos
- Ecosystem - projects using BLOC
- Tools - Direct to all BLOC softwares
- Developer Area
- Help with tutorials and guides
- Access to the private BLOC chatroom
- Backup your wallet and restore it on your computer

## **Available for multiple devices**

Access the same BLOC Dashboard account from multiple devices easily.

- Android version for mobile phone and tablet
- iOS version for iPhone and iPad
- Web version for any device using a web browser

f12878f2730940029b78199bfde73b40754764a379f5a8591fe453ba67b29e03

Presentation:
![BLOC Electron Wallet - Welcome screen](images/BLOC-gui-wallet/V3/BLOC-Electron-wallet-gif-v3.5.2.gif)

## **Screenshot**

![BLOC Electron Wallet - Welcome screen](images/BLOC-gui-wallet/V3/2-BLOC-electron-wallet-welcome.png)

**Notes**

Each BLOC wallet gets a unique set of 64 characters private keys called spendSecretKey and viewSecretKey.

- Write down your private keys. It is the only way to restore your wallet.
- Keep it secret and safe. If you save it an insecure location you might loose your funds.
- Do not store on your smartphone, tablet or computer. Only you are responsible for the security of your funds.

This is a web wallet created by BLOC Dashboard. For large amount, more security and better privacy please create a cold-storage [paper walet](../wallets/Making-a-paper-wallet.md) and use the BLOC dashboard wallet as a daily wallet. The BLOC Dashboard is safe and secure but it is an online wallet. The less funds available on this wallet, the better it is.

## **Download**

* Visit [BLOC Dashboard](https://dashboard.bloc.money) from any device with a web browser and login to your account
* Download [BLOC Dashboard for Android](https://dashboard.bloc.money) from the Google Play Store
* Download [BLOC Dashboard for iOS](https://dashboard.bloc.money) from the Apple App Store

## **Register an account**

![BLOC Electron Wallet](images/BLOC-gui-wallet/V3/1-BLOC-electron-wallet-settings.png)

1. In order to use the BLOC Dashboard you need to register an account. Go to the register page and fill the form with the required details then create tap create your account.
2. Check your email and confirm your account creation by clicking the link from the email we sent you.

## **Welcome Screen**

![BLOC Electron Wallet - Welcome screen](images/BLOC-gui-wallet/V3/2-BLOC-electron-wallet-welcome.png)

Welcome to your BLOC wallet. There is 4 differents options available.

1. Create new wallet
2. Open an existing wallet already created by the BLOC Electron Wallet Client
3. Import private keys to restore a wallet
4. Import Mnemonic seed words to restore a wallet

## **Create new wallet**<a name="create-wallet"></a>

![BLOC Electron Wallet - Create a new wallet](images/BLOC-gui-wallet/V3/3-BLOC-electron-wallet-create.png)

If this is your 1st time using BLOC or you just need to create a new wallet use this option.

1. Select where the wallet file will be stored. Click on the folder icon, choose where you woud like to save your wallet, enter the name of the file and click save.
2. Set the required password to open this wallet file
3. Click the button `CREATE A NEW BLOC WALLET`
4. Wallet file is saved with the following extension: `mywallet.money`

You should see a message: Wallet has been imported. You can now [open the wallet](../wallets/BLOC-GUI-Electron-Wallet.md#open-wallet).

## **Open an existing wallet file .money**<a name="open-wallet"></a>

BLOC Electron Wallet require a connection to a BLOC node to be able to work.
You have two possibilities:

![BLOC Electron Wallet - Open an existing wallet file .money](images/BLOC-gui-wallet/V3/4-BLOC-electron-wallet-open.png)

1. Create your own node - Download and start BLOCd on your machine locally or remotely then connect to it with BLOC Electron Wallet.
2. Use a public remote BLOC node and do not bother with the tech. Select your favorite BLOC public node and connect to it.

*Note:* Public remote node may charge extra fees per transaction.

Find out more about [BLOC remote nodes](../wallets/Using-remote-nodes.md) and how you could make extra passive income.

1. Click on the folder icon to open your system explorer and select your wallet file `(.money)`
2. Type the password for this wallet
3. Type hostname or IP address of the BLOC daemon or public node to connect to*
4. Enter RPC port number of the BLOC daemon or public node
5. Click the button `OPEN THE WALLET`

* To use a local BLOC node running on the same machine as the BLOC Electron wallet enter `127.0.0.1` as Daemon address with RPC Port: `2086`

![BLOC Electron Wallet - Open an existing wallet file .money](images/BLOC-gui-wallet/V3/opening-wallet.png)

* if you are using BLOC public remote node, you might get a notification displaying the node fee price.

![BLOC Electron Wallet - Public Node Fee notification](images/BLOC-gui-wallet/V3/node-fee-notification.png)

You are now ready to use your wallet. Please follow the next instructions on how to use your wallet.

## **Import Private Keys to restore a wallet**<a name="import-private-keys"></a>

If you already have BLOC wallet address you can import your private keys using this method.

[How to import my wallet from the BLOC Wallet iOS app. Click here](../wallets/BLOC-iOS-wallet.md#from-iphone-to-desktop)

If you were using the previous BLOC Wallet v2.0.2 you can checkout [this guide to find out how to export your wallet private keys](../wallets/BLOC-GUI-Desktop-Wallet-V2.md#1-export-key-best-solution) and follow this procedure to restore your wallet:

This will restore your wallet address, funds present on it but also the complete history of your transactions. All you need is your private view key & spend key.

![BLOC Electron Wallet - Import private keys to restore a wallet](images/BLOC-gui-wallet/V3/import-private-keys.png)

1. Select where the wallet file will be stored. Click on the folder icon, choose where you woud like to save your wallet, enter the name of the file and click save.
2. Set the required password to open this wallet file
3. Select the block number from where to start scanning the blockchain for transactions contains into your wallet.
4. Enter the private view key of the wallet to be imported
5. Enter the private spend key of the wallet to be imported
6. Click the button `IMPORT PRIVATE KEYS AND RESTORE THE WALLET`

You should see a message: Wallet has been imported. You can now [open the wallet](../wallets/BLOC-GUI-Electron-Wallet.md#open-wallet).

## **Import Mnemonic seed words to restore a wallet**<a name="import-mnemonic-seed"></a>

If you already have BLOC wallet created since the BLOC V3.0 you should already have a Mnemonic seed. You can import it using this method.

This will restore your wallet address, funds present on it but also the complete history of your transactions. All you need is your Mnemonic seed words list.

![BLOC Electron Wallet - Import Mnemonic seed to restore a wallet](images/BLOC-gui-wallet/V3/import-Mnemonic-seed.png)

1. Select where the wallet file will be stored. Click on the folder icon, choose where you woud like to save your wallet, enter the name of the file and click save.
2. Set the required password to open this wallet file
3. Select the block number from where to start scanning the blockchain for transactions contains into your wallet.
4. Enter the Mnemonic seed words of the wallet to be imported
5. Click the button `IMPORT MNEMONIC SEED AND RESTORE THE WALLET`

You should see a message: Wallet has been imported. You can now [open the wallet](../wallets/BLOC-GUI-Electron-Wallet.md#open-wallet).


## **Wallet Overview**

We will have to wait for the wallet synchronisation to finish in order to use the wallet.

![BLOC Electron Wallet - Wallet Overview](images/BLOC-gui-wallet/V3/wallet-overview.png)

The overview display all the important informations about your wallet such as:

1. `Balance` (Available and Locked)
2. `Status` gives you the synchronisation state of the wallet. (The 1st number is the actual block synched to this wallet and the second number is last known top block on the network)
3. `Connected To` display the current node you are connected to use your wallet
4. `Node fee` shows the fee amount used by this node for each transaction.
5. `Your wallet address` that can be shared to your customers/friends so they can pay you
6. `QR Code` makes it even easier to share your BLOC address. Scan to share.
6. `BLOC Price` display BLOC price from CoinGecko
6. `OPTIMIZE` button optimize your wallet to send larger amount transactions. Required if you are mining with this address and receive a lot of small transactions.


## **Send BLOC**

Send/Transfer BLOC.MONEY to any other BLOC wallet address.

![BLOC Electron Wallet - Send BLOC](images/BLOC-gui-wallet/V3/send-bloc.png)

1. Type the amount you would like to send
2. Enter the recipient address
3. The fees are set automatically to 0.0001 BLOC
1. If the receiver provided you with a Payment ID you can enter it here, it must contain 64 caracters
5. Once you are ready click. `PROCEED BLOC PAYMENT`

![BLOC Electron Wallet - Send BLOC](images/BLOC-gui-wallet/V3/send-confirm.png)

Confirm all the informations are correct.
If everything is ok click `POK SEND IT` or `CANCEL` button to return to previous screen
Transactions are sent in real time.

![BLOC Electron Wallet - Send BLOC](images/BLOC-gui-wallet/V3/send-sent.png)

You can checkout the Transaction Hash (Tx. hash) provided for your transaction at the bottom part.
If an error happen it will appear here.

## **Transactions**

Transactions list all incomming and outgoing transactions from this wallet.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/transactions.png)

- Search transaction by transaction hash or payment ID
- Transactions can be sorted by amount, date or status
- Click on a transaction to get more details
- Export transactions as .csv file

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/transaction-details.png)

You can also view the transaction on the block explorer.

## **Address Book**

Each time you send a transaction using the BLOC Electron wallet the BLOC address of the receiver will be saved into your contacts.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/contacts.png)

You can also add a beneficiary into the address book very easy. Simply enter the BLOC address, payment ID if you have one and the label to remember the name of this beneficiary. Once ready click `Save contact` button.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/contacts-added.png)

## **BLOC Explorer**

Our crypto currency BLOC explorer shows the latest blocks in the blockchain. Clicking on a specific network block will provide you with more information regarding its size, when it was found, and more importantly, which transactions it contains.

Our BLOC explorer is also a valuable tool to see how the current block reward is distributed to the miners.
BLOC explorer can also search for Payment IDs, Block hash, Block height, Transaction hash.

The BLOC explorer quickly become your best friend to verify transactions on the Ƀ BLOC blockchain network.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/bloc-explorer.png)

- Click the `BLOC EXPLORER WEBSITE` button to visit the official [BLOC-EXPLORER](https://bloc-explorer.com)
- If you are using Telegram® we made a [`TELEGRAM BOT EXPLORER`](https://t.me/bloc_explorer_bot) to check for a transaction and get informations without having to quit your favorite messenger.

## **Tools**

Discover and download the exlusive range of [BLOC.MONEY (BLOC) softwares](https://bloc.money/download) from the tools section.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/tools.png)

## **News**

Stay up to date with the latest news from the official [BLOC medium blog](https://medium.com/@bloc.money).

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/news.png)

## **Videos**

Watch the latest videos from the [BLOC.MONEY (BLOC) Youtube channel](https://www.youtube.com/channel/UCdvnEPWhqGtZUEx3EFBrXvA).

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/videos.png)

## **Ecosystem**

Use, spend, buy and sell your BLOC.money (BLOC). Discover the [powerful BLOC ecosystem](https://bloc.money/ecosystem).

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/ecosystem.png)

## **Help**

This wiki is the main source of documentation for newcomers to the [BLOC Project](https://github.com/furiousteam/BLOC). If this is your first time hearing about BLOC, we recommend starting by visiting the official [BLOC.MONEY](https://bloc.money) website.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/bloc-wiki.png)

## **Exchange**

Find here the list where to trade BLOC with other cryptocurrencies.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/exchange.png)

## **Miner**

If you want to learn about cryptocurrencies, mining is a great place to start!. 
The BLOC Electron wallet include a built-in miner for BLOC which makes it very easy to use with a one single click button to start mining.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/miner.png)

The advantages of the miner built-in the BLOC Electron wallet:

- The miner will not be detected as virus like any other mining software
- Very easy to use with 1 click button to start mining using your built-in BLOC address
- Complete mining stats provided
- Mining from the official [POOL.BLOC.MONEY](https://pool.bloc.money).
- CPU Mining only

Once the mining is made easy, this is not the best solution if you want to mine regulary BLOC. If you are interested about mining and looking for a more efficient solution we suggest you to look at the [BLOC GUI Miner](../mining/BLOC-GUI-Miner.md)

To start mining simply swich ON the button.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/miner-mining.png)

Notice a yellow box will appears on the left menu while browsing the other sections to remember you that you are mining.

## **Backup**

Backup your wallet with your private keys so you can restore your wallet anytime.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/backup.png)

To display the private keys of your wallet click the `REVEAL THE KEYS AND MMEMONIC SEED` button.

The private keys below can restore your wallet using the BLOC Electron Wallet or the [BLOCWallet](../wallets/BLOCWallet-how-to-use.md). Never share this keys with anyone.

![BLOC Electron Wallet - Transactions](images/BLOC-gui-wallet/V3/backup-keys.png)

Click `EXPORT TO FILE` button to export the private keys of your wallet into a file.

### 25 Word Mnemonic Seed phrase not showing ?!
Some of the BLOC address do not have 25 Word Mnemonic Seed phrase because they were created inside a commun wallet container or it has been created before we implemented this feature.
# Using BLOCWallet Cli

The **CLI Wallet**, called **BLOCWallet**, is a multi-platform program (Win/Linux/Mac) that requires you to enter commands for it to work and you cannot use your mouse. It is text only application that does not have a graphical interface. However, it is currently the most stable and gets the newest updates first.

Here's a quick image of `BLOCWallet` in action:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0.png)

## **Downloading**

* Binary distributions can be found: [here](https://github.com/furiousteam/BLOC/releases/latest).
* Select the appropriate file for the target platform (Windows, Mac, Linux).
* Binaries are provided in `.zip` format, while source code is provided in `.zip` and `.tar.gz` format.

## **Installing**

### Installing on Windows

Extract the *.zip* file (`BLOC-...-windows.zip`).

### Installing on Mac

Extract the *.zip* file:

```bash
unzip BLOC-...-mac.zip
```

### Installing on Linux

Extract the *.zip* file:

```bash
unzip BLOC-...-linux.zip
```

## **Synchronizing the Blockchain**

Here's a quick image of `BLOCd MAIN NET` in action:

![BLOCd MAIN NET](images/BLOCd/BLOC-MAINNET-3.0.0.1.png)

Here's a quick image of `BLOCd TEST NET` in action:

![BLOCd TEST NET](images/BLOCd/BLOC-TESTNET-3.0.0.1.jpg)

Running `BLOCd` will start the *BLOCd* network daemon, which will connect to the network and begin downloading and verifying the BLOC blockchain.  

Because the blockchain is constantly growing, the file size always increases (the blockchain is currently over 2 GB), and *BLOCd must verify every block*, which is both CPU and disk intensive. An SSD with at least this much free disk space is recommended, unless you plan to use [remote nodes](../Using-remote-nodes). 

## **Using Checkpoints**

You can sync a fresh chain from block 0 much quicker by using checkpoints. Follow [this guide](../Using-checkpoints-for-BLOCd.md) to learn more.

### Windows

Run the `BLOCd.exe` executable extracted from the Windows binary zip:

### Mac / Linux

Run the `BLOCd` binary extracted from the `.zip` download:

```bash
./BLOCd
```

## **Using BLOCWallet**

With `BLOCd` still running in the background or another terminal/shell/command prompt, open BLOCWallet:

### Windows

Run the `BLOCWallet.exe` executable from the extracted folder.

### Mac / Linux

```bash
./BLOCWallet
```

## **Using BLOCWallet commands**

BLOCWallet has a twin command system; a numerical shortcut for navigating the menu, and typed commands you can access directly. The more you use BLOCWallet the more typed commands you'll pick up. This guide is written using the written commnand system. Feel free to use the numbers associated with the command.

## **Creating a Wallet**

Create your personnal BLOC Wallet address with Private spend key, Private view key and Mnemonic seed. Everything you need to control your money.
Make sure you save this data because if you lose these keys your wallet cannot be recreated!

Here's a quick image of BLOCWallet in action after have successfully `created a wallet`:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0.png)

To create a wallet, type `create` `2` or and press `enter`:

```
What would you like to do?: 2
What would you like to call your new wallet?: JENNY
Give your new wallet a password: ****
Confirm your new password: ****
Welcome to your new wallet, here is your payment address:
abLoc8oL14r8DUdzXBPwN8LPMSBJfS3BaFG96gQPhFWRNBw2g6AHpFoJyuYP7h83cPEcLYxKAgMs9L27S3tBNEHaMkR6JhDsLt5

Please copy your secret keys and mnemonic seed and store them in a secure location: 
Private spend key:
cda47a19e5d433060ab79c885817cd20fc394dc7043ac875678a3698804ede01

Private view key:
e82ebf49b74fccd754e39ac3ca6fabca35277b012dfce0cf8921c216396b3108

Mnemonic seed:
jazz border dude orphans worry absorb slackens public drinks bovine evenings hurried roped jaws drinks snug directed pirate behind zero null cuisine agreed alchemy directed

If you lose these your wallet cannot be recreated!


Your wallet is syncing with the network in the background.
Until this is completed new transactions might not show up.
Use the status command to check the progress.

 1	advanced                 List available advanced commands
 2	address                  Display your payment address
 3	balance                  Display how much BLOC you have
 4	backup                   Backup your private keys and/or seed
 5	exit                     Exit and save your wallet
 6	help                     List this help message
 7	transfer                 Send BLOC to someone

[BLOC JENNY]: 

```
## **Opening a Wallet**

Open an existing wallet file **created by BLOCWallet v3.0**. BLOCWallet v3.0 also supports the following :

* .wallet file created by the [BLOC Desktop Wallet & Mining Client v2](../Using-BLOCWallet#bloc-desktop-2.0.2)
* .wallet file created by the previous BLOC Simple Wallet v2

Here's a quick image of BLOCWallet in action after have successfully `open a wallet`:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet.png)

To open an existing wallet; type `open` or `1` and press `enter`:

```
 1	open                     Open a wallet already on your system
 2	create                   Create a new wallet
 3	seed_restore             Restore a wallet using a seed phrase of words
 4	key_restore              Restore a wallet using a view and spend key
 5	view_wallet              Import a view only wallet
 6	exit                     Exit the program

What would you like to do?: 1
What is the name of the wallet you want to open?: JENNY
Enter password: ****

Making initial contact with BLOCd.
Please wait, this sometimes can take a long time...


Your wallet abLoc8oL14r8DUdzXBPwN8LPMSBJfS3BaFG96gQPhFWRNBw2g6AHpFoJyuYP7h83cPEcLYxKAgMs9L27S3tBNEHaMkR6JhDsLt5 has been successfully opened!

Scanning through the blockchain to find any new transactions you received
whilst your wallet wasn't open.
Please wait, this may take some time.

101819 of 101827
101819 of 101827

Finished scanning blockchain!

 1	advanced                 List available advanced commands
 2	address                  Display your payment address
 3	balance                  Display how much BLOC you have
 4	backup                   Backup your private keys and/or seed
 5	exit                     Exit and save your wallet
 6	help                     List this help message
 7	transfer                 Send BLOC to someone

[BLOC JENNY]: 

```
## **Viewing Wallet Address**

Display the BLOC address used by this wallet.

* MAIN NET BLOC address start with `abLoc`
* TEST NET BLOC address start with `TbLoc`

Here's a quick image of BLOCWallet in action after have successfully typed `address`:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet_address.png)

To view a wallet's public address; at the menu, type `address` or `2` and press `enter`.

```
[BLOC JENNY]: address
abLoc8oL14r8DUdzXBPwN8LPMSBJfS3BaFG96gQPhFWRNBw2g6AHpFoJyuYP7h83cPEcLYxKAgMs9L27S3tBNEHaMkR6JhDsLt5
[BLOC JENNY]: 
```

## **Exporting Keys**

Each BLOC wallet is essentially, just a pair of keys (*View Key* and *Spend Key*) from which the public address is derived.
It is **very** important to export these keys and back them up somewhere that is safe and secure (meaning somewhere reliable/permanent that no one else can access).

In the event of a lost or corrupted wallet file, computer crash, etc., the *View Key* and *Spend Key* are the only way to restore a wallet and recover the funds it holds.

Here's a quick image of BLOCWallet in action after using the `backup` command:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet_backup.png)

**DO NOT SHARE IT WITH ANYONE**. **Anyone who has these can *access your funds* and has *complete control* over your wallet.**

To print your keys; at the menu type `backup` or `4`and press `enter`.
The *View Key* and *Spend Key* will appear. Copy them and store them `safely and securely`.

```
[BLOC JENNY]: backup
Enter password: ****
Private spend key:
cda47a19e5d433060ab79c885817cd20fc394dc7043ac875678a3698804ede01

Private view key:
e82ebf49b74fccd754e39ac3ca6fabca35277b012dfce0cf8921c216396b3108

Mnemonic seed:
jazz border dude orphans worry absorb slackens public drinks bovine evenings hurried roped jaws drinks snug directed pirate behind zero null cuisine agreed alchemy directed
[BLOC JENNY]: 

```

### 25 Word Mnemonic Seed phrase not showing ?!

![blocwallet](images/BlocWallet/backup-old.png)

* You may wonder why you do not see the new 25 Word Mnemonic Seed phrase while typing `backup` your wallet ?
* The 25 Word Mnemonic Seed phrase was implemented after you created this wallet. This is why you do not see the 25 Word Mnemonic seed.
* You will need to create a new wallet to be able to use the 25 Word Mnemonic seed and send your BLOC to your new wallet

## **Viewing Wallet Balance**

* Available balance is the funds that are available for transactions.
* Locked amount shows the funds that are not yet available (unconfirmed transactions, the coins you've mined, time-locked transaction)
* Total

Here's a quick image of BLOCWallet in action after using the `balance` command:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet_balance.png)

To view your wallet's balance; at the menu, type `balance` or `3` and press `enter`:

```
[BLOC JENNY]: balance
Available balance: 1.0000 BLOC
Locked (unconfirmed) balance: 0.0000 BLOC
Total balance: 1.0000 BLOC
[BLOC JENNY]:
```

## **Sending BLOC Transactions**<a name="tx-bloc"></a>

Send funds from your wallet to your friends, family or for business.

Here's a quick image of BLOCWallet in action after using the `transfer` command:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet_transfer.png)

To send BLOC at the BLOCWallet menu:

- Type: `transfer` or `7` and press `enter`
- Type/paste the address you want to send the BLOC to and press `enter`
- Type the amount of BLOC you want to send (like `0.5`) and press `enter`
- Press `enter` to use the default fee of 0.0001 BLOC (or set it higher if you're sending a large amount of BLOC)
- Enter the payment ID if the recipient has provided one. Check the [payment ID section](#tx-bloc-p-id) if you're not sure when/how to use it
- If you make a mistake or need to stop the transaction, type `cancel` at any time
- Confirm that the details are correct and enter `y`. If something is amiss, enter `n` and follow the steps again
- Enter your password

Depending on the amount you transfer, you may need to wait a while for confirmation.  If you have had too many small incoming transactions, or the amount you wish to send is too large; either break up your transfer into several smaller amounts, or optimise your wallet.

## **Optimizing your Wallet**

Fusion transactions take all your (small) incoming payments and combine them into bigger ones, allowing you to send huge sums at once!
It is strongly recommended to optimize your wallet, specially if you are mining BLOC and receiving a lot of small transactions.

Here's a quick image of BLOCWallet in action after using the `optimize` command:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet_optimize.png)

To optimize your wallet, type `optimize` and press `enter`:
```
[BLOC JENNY]: optimize
Attempting to optimize your wallet to allow you to send large amounts at once. 
This may take a very long time!
Do you want to proceed? (Y/n): y
Running optimization round 1...
Full optimization completed!
[BLOC JENNY]: 
```

When it is completed, it will print out a green message `Full optimization completed!`

## **Payment ID**<a name="tx-bloc-p-id"></a>

Because transactions on the BLOC blockchain are privatized, in some situations a payment ID is necessary for the recipient to be able to determine where the payment came from, for instance when depositing to an exchange or other service.

**You need it if you're sending BLOC to an exchange**

Here's a quick image of BLOCWallet in action after using the payment id option while sending a transaction:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet_payement-id.png)

To send a transaction with a payment ID, enter it when prompted to.

Note that typically, the service/recipient will generate and provide the required payment ID.
```
[BLOC JENNY]: transfer
Note: You can type cancel at any time to cancel the transaction

What address do you want to transfer to?: abLoc7qZYJd7cWysPQRivNNMQMFgkXNPgiQXN1i2twdUWvwr2XMbxsAbwdL3eJjCMSgs8oWyGx7pHCX8jWHrKi8Meap3gc5TujM

How much BLOC do you want to send?: 0.1

What fee do you want to use?
Hit enter for the default fee of 0.0001 BLOC: 

What payment ID do you want to use?
These are usually used for sending to exchanges.
Warning: If you were given a payment ID,
you MUST use it, or your funds may be lost!
Hit enter for the default of no payment ID: 399c9805d2fbcae432b83a62279e3e9f00a96d05ec7edc8f14599a91baaf1213

Confirm Transaction?
You are sending 0.1000 BLOC, with a network fee of 0.0001 BLOC,
and a node fee of 0.0000 BLOC, 
and a Payment ID of 399c9805d2fbcae432b83a62279e3e9f00a96d05ec7edc8f14599a91baaf1213

FROM: JENNY.wallet
TO: abLoc7qZYJd7cWysPQRivNNMQMFgkXNPgiQXN1i2twdUWvwr2XMbxsAbwdL3eJjCMSgs8oWyGx7pHCX8jWHrKi8Meap3gc5TujM

Is this correct? (Y/n): y
Enter password: ****
Transaction has been sent!
Hash: f1259467fe4c79c091c05f9fe335bda6f45ef8ac995e25a0909ca73a1b5973f8
[BLOC JENNY]: 
```

## **Exiting the Wallet**

Wallets loaded into the *BLOCWallet* client must be synced with the blockchain in order to properly calculate balance, view transaction history, etc.

It is important to properly save the wallet data before exiting *BLOCWallet* so that the synchronized data is not lost.

Here's a quick image of BLOCWallet in action after using the `exit` option while closing BLOCWallet :

![blocwallet](images/BlocWallet/exit.png)

To save a wallet's data and exit; at the menu, type `exit` or `5` and press `enter`:

```
[BLOC JENNY]: exit
Shutting down...
Saving wallet file...
Shutting down wallet interface...
Shutting down node connection...
Bye.
```

## **Recovering your Wallet**

Recovering your wallet on BLOC is easy and fast.

### With Private Spend and View Keys<a name="recover-spend-view-keys"></a>

Here's a quick image of BLOCWallet in action after using the `key_restore` command while restoring a wallet:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet_key_restore.png)

To restore a wallet using spend and view keys; at the menu type `key_restore` or `4` and press `enter`:

```
1	open                     Open a wallet already on your system
 2	create                   Create a new wallet
 3	seed_restore             Restore a wallet using a seed phrase of words
 4	key_restore              Restore a wallet using a view and spend key
 5	view_wallet              Import a view only wallet
 6	exit                     Exit the program

What would you like to do?: key_restore
Enter your private spend key: cda47a19e5d433060ab79c885817cd20fc394dc7043ac875678a3698804ede01
Enter your private view key: e82ebf49b74fccd754e39ac3ca6fabca35277b012dfce0cf8921c216396b3108
What would you like to call your new wallet?: JENNY
Give your new wallet a password: ****
Confirm your new password: ****
What height would you like to begin scanning your wallet from?

This can greatly speed up the initial wallet scanning process.

If you do not know the exact height, err on the side of caution so transactions do not get missed.

Hit enter for the sub-optimal default of zero: 

Making initial contact with BLOCd.
Please wait, this sometimes can take a long time...

Your wallet abLoc8oL14r8DUdzXBPwN8LPMSBJfS3BaFG96gQPhFWRNBw2g6AHpFoJyuYP7h83cPEcLYxKAgMs9L27S3tBNEHaMkR6JhDsLt5 has been successfully imported!

Scanning through the blockchain to find transactions that belong to you.
Please wait, this will take some time.

1 of 101848
1 of 101848
....
101377 of 101850
101575 of 101850
101773 of 101850

New transaction found!

Incoming transfer:
Hash: c4e2d9b972a2e70a209428fe5e6b367b632a3407f0d1486949ed8da75642cf10
Block height: 101833
Timestamp: 2018-10-25 14:29
Amount: 1.0000 BLOC

Finished scanning blockchain!

 1	advanced                 List available advanced commands
 2	address                  Display your payment address
 3	balance                  Display how much BLOC you have
 4	backup                   Backup your private keys and/or seed
 5	exit                     Exit and save your wallet
 6	help                     List this help message
 7	transfer                 Send BLOC to someone

[BLOC JENNY]: 

```

### With mnemonic phrase (25 words)<a name="recover-seed"></a>

Here's a quick image of BLOCWallet in action after using the `seed_restore` command while restoring a wallet:

![blocwallet](images/BlocWallet/BLOCWallet_v3.0.0_open_wallet_seed_restore.png)

To restore a wallet using spend and view keys; at the menu type `seed_restore` or `3` and press `enter`:

```
 1	open                     Open a wallet already on your system
 2	create                   Create a new wallet
 3	seed_restore             Restore a wallet using a seed phrase of words
 4	key_restore              Restore a wallet using a view and spend key
 5	view_wallet              Import a view only wallet
 6	exit                     Exit the program

What would you like to do?: 3
Enter your mnemonic phrase (25 words): jazz border dude orphans worry absorb slackens public drinks bovine evenings hurried roped jaws drinks snug directed pirate behind zero null cuisine agreed alchemy directed
What would you like to call your new wallet?: JENNY
Give your new wallet a password: ****
Confirm your new password: ****
What height would you like to begin scanning your wallet from?

This can greatly speed up the initial wallet scanning process.

If you do not know the exact height, err on the side of caution so transactions do not get missed.

Hit enter for the sub-optimal default of zero: 101000

Making initial contact with BLOCd.
Please wait, this sometimes can take a long time...


Your wallet abLoc8oL14r8DUdzXBPwN8LPMSBJfS3BaFG96gQPhFWRNBw2g6AHpFoJyuYP7h83cPEcLYxKAgMs9L27S3tBNEHaMkR6JhDsLt5 has been successfully imported!

Scanning through the blockchain to find transactions that belong to you.
Please wait, this will take some time.

1 of 101852
1 of 101852
100882 of 101852
101179 of 101852
101575 of 101852

New transaction found!

Incoming transfer:
Hash: c4e2d9b972a2e70a209428fe5e6b367b632a3407f0d1486949ed8da75642cf10
Block height: 101833
Timestamp: 2018-10-25 14:29
Amount: 1.0000 BLOC

Finished scanning blockchain!

 1	advanced                 List available advanced commands
 2	address                  Display your payment address
 3	balance                  Display how much BLOC you have
 4	backup                   Backup your private keys and/or seed
 5	exit                     Exit and save your wallet
 6	help                     List this help message
 7	transfer                 Send BLOC to someone

[BLOC JENNY]: 

```

## **Open a old wallet file BLOC Wallet v2.0.2 <a name="bloc-desktop-2.0.2"></a>

Restore your wallet file from the previous [BLOC Wallet Desktop v2.0.2](../BLOC-GUI-Desktop-Wallet-V2)

* Follow the standard procedure explained on this page and launch the new BLOCWallet v3.0 Client

* Copy/Paste the wallet file near the BLOCWallet:

![blocwallet](images/BlocWallet/restore-file.png)

* Open BLOCWallet

![blocwallet](images/BlocWallet/restore-file-2.png)

* Select Option: 1 (Open)
* Enter the name of your wallet file without the extension. Here: MYWALLET
* Enter the password

![blocwallet](images/BlocWallet/restore-file-3.png)

* Your wallet has been successfully synchronised.
* You can trype `balance` to check the balance of your wallet

![blocwallet](images/BlocWallet/restore-file-4.png)

### 25 Word Mnemonic Seed phrase not showing ?!

![blocwallet](images/BlocWallet/backup-old.png)

* You may wonder why you do not see the new 25 Word Mnemonic Seed phrase while typing `backup` your wallet ?
* The 25 Word Mnemonic Seed phrase was implemented after you created this wallet. This is why you do not see the 25 Word Mnemonic seed.
* You will need to create a new wallet to be able to use the 25 Word Mnemonic seed and send your BLOC to your new wallet

## Other Commands

To see a list of additional commands not already covered; at the menu type `advanced` or `1` and press `enter`:

```
 1	advanced                 List available advanced commands
 2	address                  Display your payment address
 3	balance                  Display how much BLOC you have
 4	backup                   Backup your private keys and/or seed
 5	exit                     Exit and save your wallet
 6	help                     List this help message
 7	transfer                 Send BLOC to someone

[BLOC JENNY]: advanced

 8	ab_add                   Add a person to your address book
 9	ab_delete                Delete a person in your address book
 10	ab_list                  List everyone in your address book
 11	ab_send                  Send BLOC to someone in your address book
 12	change_password          Change your wallet password
 13	make_integrated_address  Make a combined address + payment ID
 14	incoming_transfers       Show incoming transfers
 15	list_transfers           Show all transfers
 16	optimize                 Optimize your wallet to send large amounts
 17	outgoing_transfers       Show outgoing transfers
 18	reset                    Recheck the chain from zero for transactions
 19	save                     Save your wallet state
 20	save_csv                 Save all wallet transactions to a CSV file
 21	send_all                 Send all your balance to someone
 22	status                   Display sync status and network hashrate
```

## Help

To see the main menu of commands; type `help` and press `enter`:

```
[BLOC JENNY]: help

 1	advanced                 List available advanced commands
 2	address                  Display your payment address
 3	balance                  Display how much BLOC you have
 4	backup                   Backup your private keys and/or seed
 5	exit                     Exit and save your wallet
 6	help                     List this help message
 7	transfer                 Send BLOC to someone

```


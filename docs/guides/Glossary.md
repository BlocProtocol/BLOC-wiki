# **Glossary**

Glossary of the most important [BLOC](https://bloc.money) terms

## **Public address**

Also known as your address or wallet address. An example of a valid BLOC address looks like this:

**MAIN NET:**
```
abLoc7qZYJd7cWysPQRivNNMQMFgkXNPgiQXN1i2twdUWvwr2XMbxsAbwdL3eJjCMSgs8oWyGx7pHCX8jWHrKi8Meap3gc5TujM
```
**TEST NET:**
```
TbLoc4j9YWbi4RJie7w13WSJ4akG4c5Fxc8bgX5QPiENQYYjriYjesRdbPWix7qKSUUBK4oRcJHG4J519686WaLy131qpCxBq2q
```

## **Payment id** <a name="payment-id">

When someone sends you funds, they can specify a payment ID of their or your choice. Because BLOC's privacy protections usually prevent you from knowing the source of funds that you receive, the payment ID can be used by the sender to identify themselves to you. The payment ID must contain a 64 HEX string. You can use this website to generate a custom [64 HEX payement ID](https://www.browserling.com/tools/random-hex).

In some situations a payment ID is necessary for the recipient to be able to determine where the payment came from, for instance when depositing to an exchange or other service.

* Example: 4126541177d951210fa7d8f8bfabcd76b3a839724248f1b3404e5785fa506e62

## **Integrated payment address** <a name="integrated-address">

Integrated address is just your normal address with some extra data bundled with it (the 64-bit payment ID). To make it easier for other people to send you funds with a payment ID that you require, you can generate an integrated address to send to them which contains both your public address and the payment ID you request them to use.

## **Wallet / wallet files / wallet software**

Your wallet holds your private key, which allows you to view your funds and spend them. A wallet may be configued to only hold a view key, so that the wallet can observe your funds but not spend them. Your wallet also contains a list of transaction IDs and transaction keys, which allow you to see a list of payments you've previously made.

If you create another wallet from your seed (which is a representation of your private key), then you will have the full ability to spend your funds and you will be able to see a list of transactions that you've previously made.

'Wallet' may refer to just the wallet files on your computer, or additionally to the wallet software that you run which allows you to view your wallet files and transact. Your wallet communicates with a BLOC daemon to scan the blockchain for incoming transactions and to send new transactions.

## **Private key / Seed**

Your private key is what allows you to spend your funds. Your 'seed' is just a 25 word representation of your private key which is easy for you to write down on paper. You must keep your private key a secret, or other people will be able to spend your funds. Your private key is the only thing you need to access and spend your funds. Your public address can be recovered from your private key, so you do not need to additionally keep a note of your public address.

## **View key, also known as a secret view key or private view key**

Your view key is normally kept private. If you wish, you can give out your view key so that others can observe the contents of your wallet. For security reasons, you may use your own view key to observe your funds on a computer which may be at risk of attack. Therefore if that computer became compromised, the attacker could see that you have funds, but not be able to steal them. Your private key would be kept safe and only used when you need to send funds when on a more secure computer.

## **Daemon**

'Daemon' is a technical term for a program that runs in the background. BLOC uses a daemon to synchronize with the BLOC network to scan for incoming transactions and to send new transactions. Your wallet needs to use the daemon to scan the entire blockchain for incoming transactions, because only your wallet has your private view key. Only your private view key can be used to detect which transactions on the BLOC network have been sent to you. This is a key part of BLOC's privacy technology.

## **Balance / Unlocked balance**

When someone sends you funds, they will appear in your balance. Once the BLOC network has 'confirmed' the transaction which will take on average 4 minutes (2 confirmations), your funds will become spendable and will be listed as part of your 'unlocked' balance. The 2 confirmation minimum is necessary to prevent double spending by the sender.

## **Refresh / synchronization**

Because of BLOC's privacy mechanisms, your private view key needs to be used to scan the blockchain to detect transactions destined for you. This means that until your wallet software has scanned the entire blockchain, you will not see your funds appear in your wallet's balance.

## **Mining / Blocks / Blockchain**

Mining is the process by which the network of BLOC nodes collectively verifies transactions, in exchange for a small transaction fee. When transactions are mined, this causes them to appear in a block, which is added to the blockchain. The blockchain is therefore the entire record of all BLOC transactions that have ever taken place. BLOC's privacy mechanisms ensure that the blockchain can only be used to reveal information about transactions to those involved in the transaction. The blockchain is necessary to prevent the double-spending of funds, because it contains the information necessary to verify that funds have not already been spent by their owner.

## **Mining pool**

A group of computers that together run mining software to process BLOC transactions and collectively share in the reward. The advantage of a Mining pool is that a single computer would take too long to mine a single block if it were working alone, and so the owner of the computer would have to wait unreasonably long to receive their first share of the mining rewards.

## **Privacy level / mixin**

When you send funds, BLOC's privacy mechanism will obscure your funds as a possible source by 'mixing in' other sources of funds in the transaction. It is impossible for any observer to know which is the real source of the funds, and only you can prove that you were the real source by deciding to reveal the secret transaction key generated by you for that transaction. 

A mixin level of 5, (the minimum allowable in the BLOC network is 0 and the maximum is 10) this might change later, will mean that your funds will appear to be one of 5 possible sources of funds for the transaction. In the GUI, the mixin level is referred to as the 'privacy level'. Remember that every other person that sends a transaction may randomly select your funds to be a plausible source in their own transaction. This means that although it may at first seem like you are one of 5 possible senders, the aggregate effect of all BLOC users constantly mixing each others' funds means your privacy level is radically higher than the number '5' would at first suggest. Over time, it will appear as if you've at some point plausibly directly or indirectly participated in transactions with most other BLOC users, even if you're hardly ever using BLOC.

## **Exchange**

A place you can go to exchange dollars, Bitcoin or other currencies for BLOC.

## **GUI**

GUI Stands for Graphical User Interface. It makes it easy for you to use BLOC.

## **CLI / Command line interface**

A text only application that does not have a graphical interface.
# **How to mine Conceal Network (CCX) with BLOC GUI Miner**

[Conceal Network](https://conceal.network) Conceal.Network is a decentralized blockchain bank, with deposits and investments paying interest rates, without involvement of financial institutions, powered by 100% open source code.

**Note**: Mining Conceal Network only works with XMRSTAK.

[BLOC GUI Miner](../mining/BLOC-GUI-Miner.md) is a beautiful, easy to use, Graphical User interface for mining multiple cryptocurrencies based on cryptonote. The BLOC GUI Miner is easy to use and makes you getting started with mining cryptocurrency on Windows, MacOS and Linux in no time.

It is aimed at getting people that have never tried mining before with a focus on accessibility, security and simplicity.

![BLOC GUI Miner Mining Conceal Network (CCX)](images/BLOC-GUI-MINER/SCREEN-CCX.jpg)

## **Install BLOC GUI Miner**

- XMRRIG do not support mining for CCX. You will need to use the BLOC GUI Miner with the XMR-STAK bundle built-in.

Some antivirus packages detect cryptocurrency miners as malware and will remove the miner as soon as it's started. In order for the BLOC GUI miner to function, you'll need to exclude the miner from being scanned by your antivirus software.

Download and Install:

- From BLOC.MONEY [Download Area](https://bloc.money/download)
- From [GitHub](https://github.com/furiousteam/GUI-miner/releases/latest)
- Follow [instructions for your system](../mining/BLOC-GUI-Miner-using.md) Windows, macOS or Linux 

## **PRE Install instruction for macOS with XMR-STAK**

Some libraries are required to be able to use XMR-STAK on macOS.

- Search for terminal on your mac application and open it
- Type: ```xcode-select --install```
- Then: ```ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```
- Then: ```brew doctor```
- Then the last one. Copy and paste:

```
brew install hwloc libmicrohttpd gcc openssl cmake
cmake . -DOPENSSL_ROOT_DIR=/usr/local/opt/openssl -DCUDA_ENABLE=OFF -DOpenCL_ENABLE=OFF
make install
```
You should now be ready to use the BLOC GUI Miner.

## **Mining Conceal Network (CCX)**

It is now very easy and fun to mine Conceal Network (CCX) using the BLOC GUI Miner.

### **Launch the BLOC GUI Miner**

Launch the BLOC GUI Miner and select **I want to mine other cryptocurrencies**

![BLOC GUI Miner Mining Conceal Network (CCX)](images/BLOC-GUI-MINER/BLOC-GUI-Miner-v0.0.3-miner-setup.png)

### **Select Conceal Network (CCX)**

Select Conceal Network (CCX)

![BLOC GUI Miner Mining Conceal Network (CCX)](images/BLOC-GUI-MINER/XMR-STAK.png)

### **Conceal Network (CCX) Address**

Enter your Conceal Network (CCX) wallet address. It must start with **ccx** and click **OK, NEXT STEP**.

![Enter mining Conceal Network (CCX)](images/BLOC-GUI-MINER/ccx-address.png)

### **Choose Mining Pool**

We suggest you to select the nearest mining pool following your location for the best mining experience and results.

Select your favorite mining pool from the list and click **OK, NEXT STEP**.

![Select Mining pool Conceal Network (CCX)](images/BLOC-GUI-MINER/ccx-pool.png)

### **Antivirus**

Some antivirus packages detect cryptocurrency miners as malware and will remove the miner as soon as it's started.

In order for the BLOC GUI miner to function, you'll need to exclude the miner from being scanned by your antivirus software.

Once you are ready click **OK,I'VE ALLOWED THE MINER**

![BLOC GUI Miner Mining Conceal Network (CCX)](images/BLOC-GUI-MINER/BLOC-GUI-Miner-v0.0.3-antivirus.png)

### **Configuring**

BLOC GUI Miner will auto configure your mining hardware with the best capabilities in the most cases. The configuration process is almost instant or take few seconds.

![BLOC GUI Miner Mining Conceal Network (CCX)](images/BLOC-GUI-MINER/BLOC-GUI-Miner-v0.0.3-ready.png)

### **Mining**

Congratulations ! You are mining **Conceal Network (CCX)** cryptocurrency. This is the overview of the BLOC GUI Miner. You can see the complete informations of your mining activity and some more details about the BLOC ecosystem.

- You can change the mining pool by clicking here. It will open the settings page.

![BLOC GUI Miner Mining Conceal Network (CCX)](images/BLOC-GUI-MINER/14-MINING-CCX.png)

### **Settings** <a name="Conceal Network (CCX)-settings"></a>

The settings page allow you to customize the miner settings:

- Choose another coin to mine
- Modify your wallet mining address
- Choose a different mining pool

![Conceal Network (CCX) Miner settings](images/BLOC-GUI-MINER/ccx-settings.png)

- Select another coin to mine from the selector
    * Enter your wallet address
    * Choose your mining pool

![Conceal Network (CCX) Settings another coin](images/BLOC-GUI-MINER/ccx-settings2.png)

Once you have made the change click the button **CLICK HERE TO SAVE THE SETTINGS**.

### **Help**

Do you need more help ? Make sure you visit this section to find out more about Conceal Network (CCX), join the community, checkout the latest updates, watch videos and much more.

![Conceal Network (CCX) Help](images/BLOC-GUI-MINER/ccx-help.png)

## **I have an issue not listed here**

If you have an issue not listed here or if you would like to add a new feature to the BLOC GUI Miner pelase visit us on [GitHub](https://github.com/furiousteam/GUI-miner) and log a new issue, alternatively, you can [contact us](../about/Community.md).
# How to Bootstrap the BLOC Blockchain

This guide will help you install a recent copy of the blockchain. This should significantly speed up the task of getting the blockchain synced up so you can use your wallet.

## Windows
1. Make sure `BLOCd.exe`, `bloc-service.exe`, and/or the GUI wallet are not running.

2. Open File Explorer and type `%APPDATA%\BLOC` and hit enter.

    ![file explorer](images/bootstrap/file_explorer.jpg)

    !!! note
        If the folder doesn't exist, just go to `%APPDATA%` instead and create a folder named `BLOC`.


3. Delete the following if they exist:
    * blockindexes.bin
    * blocks.bin
    * "DB" folder


    ---
    
    **Note**: In case it is unable to delete the files due to them being used by some other program, follow these steps:
    
    * Open Task Manager with the shortcut `Ctrl + Shift+ Escape`.
      
    * Click on `Processes`.
      
    * Click on `Image Name`.
      
    * Scroll to the bottom.
      
    * Click on `bloc-service.exe`
      
    * Click on `End Process`.
      
    * Click on `End Process` again.
      
    * Try to delete them again.
    
    ![closewallet](images/bootstrap/close_walletd.png)
    
    ---


4. [Download](#) the latest snapshot of the blockchain.

5. Move the two new downloaded files to the `%APPDATA%\BLOC` folder.

6. Start `BLOCd.exe` or the GUI wallet like you normally do.

7. See [Expected Results](#ExpectedResults) section below.



## Mac & Linux
1. Make sure `BLOCd`, `bloc-service`, and/or the GUI wallet are not running.

2. Open `Finder`.

3. Use the shortcut `Command + Shift + G` to bring up `Go to Folder`: 
![gotofolder](images/boostrap-bloc-mac-1.png)

4. Delete the following if they exist: 

    * blockindexes.bin 

    * blocks.bin 

    * "DB" folder 


5. [Download](#) the latest snapshot of the blockchain.

6. Move the two new downloaded files, `blockindexes.bin` and `blocks.bin` into the `~/.BLOC/` folder.

7. Start `BLOCd` or the GUI like you normally do.

8. See the [Expected Results](#ExpectedResults) section below.

## Expected Results if Done Correctly <a name="ExpectedResults"></a>

When you start `BLOCd` you should see this. Note that the blocksize (100246) in this example will be a different number:
```
2018-Feb-01 18:43:37.216471 INFO    Initializing core...
2018-Feb-01 18:43:37.225492 INFO    Importing blocks from blockchain storage
2018-Feb-01 18:43:37.741587 INFO    Imported block with index 1000 / 100246
2018-Feb-01 18:43:38.258202 INFO    Imported block with index 2000 / 100246
2018-Feb-01 18:43:38.928033 INFO    Imported block with index 3000 / 100246
2018-Feb-01 18:43:39.454094 INFO    Imported block with index 4000 / 100246
2018-Feb-01 18:43:40.142969 INFO    Imported block with index 5000 / 100246
2018-Feb-01 18:43:40.830674 INFO    Imported block with index 6000 / 100246
```

After it completes it will start syncing incrementally like so:
```
2018-Feb-01 18:47:48.075930 INFO    Imported block with index 100000 / 100246
2018-Feb-01 18:47:48.860470 INFO    Core initialized OK
2018-Feb-01 18:47:48.860470 INFO    Initializing p2p server...
```

If you are using the GUI wallet, you can instead view the progress by opening `walletd.log` and scrolling to the bottom.

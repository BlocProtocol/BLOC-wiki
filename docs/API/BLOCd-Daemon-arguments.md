# BLOCd Command line options

The following exemples are made using a Linux system but the concept is the same for all the OS supported by the BLOCd.

## Command line options:

This is the command line options available since the BLOCd v3.0

```
  --help                                Produce help message
  --version                             Output version information
  --os-version 
  --config-file arg (=BLOC.conf)        Specify configuration file
```

### --help

Display the help message and configuration settings.

#### Exemple

```
./BLOCd --help
```

**Expected results**

![--help](images/BLOCd/command-line-options.png)


### --version

Display the version information

#### Exemple

```
./BLOCd --version
```

**Expected results**

![--help](images/BLOCd/version.png)


### --os-version

Display the operating system version information

#### Exemple

```
./BLOCd --os-version
```

**Expected results**

![--help](images/BLOCd/os-version.png)


### --config-file arg (=BLOC.conf)

Specify a configuration file to start BLOCd. This is much more simple to use if you have a particular configuration and you do not want to type all the arguments while launching BLOCd.

#### Exemple

```
./BLOCd --config-file=BLOC.conf
```

**Expected results**

![--help](images/BLOCd/os-version.png)


## How to create a configuration file .CONF

* Create a txt file with your favorite text editor and open it.
* Check all your required parameters and enter them like in this exemple

#### Exemple

```
./BLOCd --config-file=BLOC.conf
```

**Expected results**

![--help](images/BLOCd/conf.png)





























[BLOC](https://bloc.money) believes that the cryptocurrency era will require a broader development community than just a few leading crypto platforms. For this reason, **BLOC** is providing an open platform that enables companies to build their own products using **BLOC API**. It is very easy to integrate **BLOC** payment into your website/ecommerce/phisical store/application.

**BLOC** has unfolded and advanced a set of key methods to portray universal and integrated access to act as an alternative or replace the current banking system in regards to the expensive and restricted POS contactless terminals.

We also have some specific language bindings to make integration easier. You can find more details on the [Ressources page](../API/Resources.md).

## BLOC-DEVELOPER

Make sure you visit the dedicated website [BLOC-DEVELOPER.com](https://bloc-developer.com) to find out more details and test your application.

If anything is missing or seems incorrect, please check the [GitHub issues](https://github.com/furiousteam/BLOC-wiki/issues) for existing known issues or [create a new one](https://github.com/furiousteam/BLOC-wiki/issues/new).
# TestBox
Application for emulating BTLe Devices


## Getting started
Application starts a configurable gattServer.

## Screenshots

<img src="Screenshots/MainScreen.jpg" alt="drawing" width="200" />
<img src="Screenshots/CommandScreen.jpg" alt="drawing" width="200"/>
<img src="Screenshots/AlertDialogEditConfig.jpg" alt="drawing" width="200" align="top"/>


## Features
- [Start with ADB](#Start-with-ADB)
- [Log received Commands](#Log-received-Commands)


### Start with ADB

```
adb shell am start -a android.intent.action.VIEW -n sennheiser.com.firstbluetoothtest/.MainActivity
```

Available extras:
-  `--ei mode`  *Type:* **Integer** &rarr; select automation mode

> Currently only mode 1 implemented

- `--es name` *Type:* **String** &rarr; specify configuration file name to load on start

> File must be in downloads folder

- `--ei config` *Type:* **Integer** &rarr; select config on start

> Starts with `0`

- `--ez autoStart` *Type:* **Boolean** &rarr; automatic starts gattServer and advertising when config is loaded

> will not start, if no confic is selected

- `--ez autoLog` *Type:* **Boolean** &rarr; automatic starts logging when a device is connected

Example:
```
adb shell am start -a android.intent.action.VIEW
-n sennheiser.com.firstbluetoothtest/.MainActivity 
--ei mode 1 --es name Configuration.json --ei config 0 --ez autoStart true --ez autoLog false
```
### Log received Commands

### Updating loaded Config


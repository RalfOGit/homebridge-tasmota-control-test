<p align="center">
  <a href="https://github.com/grzegorz914/homebridge-tasmota-control"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-tasmota-control/main/homebridge-tasmota-control.png" width="640"></a>
</p>

<span align="center">

# Homebridge Tasmota Control
[![verified-by-homebridge](https://badgen.net/badge/homebridge/verified/purple)](https://github.com/homebridge/homebridge/wiki/Verified-Plugins)
[![npm](https://badgen.net/npm/dt/homebridge-tasmota-control?color=purple)](https://www.npmjs.com/package/homebridge-tasmota-control) 
[![npm](https://badgen.net/npm/v/homebridge-tasmota-control?color=purple)](https://www.npmjs.com/package/homebridge-tasmota-control)
[![npm](https://img.shields.io/npm/v/homebridge-tasmota-control/beta.svg?style=flat-square)](https://www.npmjs.com/package/homebridge-tasmota-control)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/grzegorz914/homebridge-tasmota-control.svg)](https://github.com/grzegorz914/homebridge-tasmota-control/pulls)
[![GitHub issues](https://img.shields.io/github/issues/grzegorz914/homebridge-tasmota-control.svg)](https://github.com/grzegorz914/homebridge-tasmota-control/issues)

Homebridge plugin for Tasmota flashed devices.

</span>

## Package Requirements
| Package | Installation | Role | Required |
| --- | --- | --- | --- |
| [Homebridge](https://github.com/homebridge/homebridge) | [Homebridge Wiki](https://github.com/homebridge/homebridge/wiki) | HomeKit Bridge | Required |
| [Config UI X](https://github.com/oznu/homebridge-config-ui-x/wiki) | [Config UI X Wiki](https://github.com/oznu/homebridge-config-ui-x/wiki) | Web User Interface | Recommended |
| [Tasmota Control](https://www.npmjs.com/package/homebridge-tasmota-control) | `npm install -g homebridge-tasmota-control` | Plug-In | Required |

## Note
* Right now only switch/outlets devices are supported.
* Tested with Tasmota 10.1.0 and above

## Troubleshooting
* If for some reason the device is not displayed in HomeKit app try this procedure:
   * Go to `./homebridge/persist` macOS or `/var/lib/homebridge/persist` for RPI.
   * Remove `AccessoryInfo.xxx` file which contain Your device data: `{"displayName":"Tasmota"}`.
   * Next remove `IdentifierCashe.xxx` file with same name as `AccessoryInfo.xxx`.
   * Restart Homebridge and try add it to the Home app again.

### Configuration
* Run this plugin as a child bridge (Highly Recommended).
* Install and use [Homebridge Config UI X](https://github.com/oznu/homebridge-config-ui-x/wiki) to configure this plugin (Highly Recommended). 
* The sample configuration can be edited and used manually as an alternative. See the `sample-config.json` file in this repository for an example or copy the example below into your config.json file, making the apporpriate changes before saving it. Be sure to always make a backup copy of your config.json file before making any changes to it.

<p align="left">
  <a href="https://github.com/grzegorz914/homebridge-tasmota-control"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-tasmota-control/master/graphics/ustawienia.png" width="840"></a>
</p>

| Key | Description | 
| --- | --- |
| `name` | Here set the accessory *Name* to be displayed in *Homebridge/HomeKit*. |
| `host` | Here set the *Hsostname or Address IP* of the Device.|
| `auth` | If enabled, authorizatins credentials will be used for login. |
| `user` | Here set the authorization *Username*. |
| `passwd` | Here set the authorization *Password*. |
| `enableDebugMode` | This enable deep log in homebridge console. |
| `disableLogInfo` | This disable log info, all values and state will not be displayed in Homebridge log console. |

```json
{
      "platform": "tasmotaControl",
      "devices": [
        {
        "name": "Outlet",
        "host": "192.168.0.4",
        "auth": false,
        "user": "user",
        "passwd": "password",
        "refreshInterval": 5,
        "disableLogInfo": false,
        "enableDebugMode": false,
      }
    ]
  }
```

### Adding to HomeKit
* Each accessory needs to be manually paired. 
  * Open the Home <img src='https://user-images.githubusercontent.com/3979615/78010622-4ea1d380-738e-11ea-8a17-e6a465eeec35.png' width='16.42px'> app on your device. 
  * Tap the Home tab, then tap <img src='https://user-images.githubusercontent.com/3979615/78010869-9aed1380-738e-11ea-9644-9f46b3633026.png' width='16.42px'>. 
  * Tap *Add Accessory*, and select *I Don't Have a Code, Cannot Scan* or *More options*. 
  * Select Your accessory and press add anyway. 
  * Enter the PIN or scan the QR code, this can be found in Homebridge UI or Homebridge logs.
  * Complete the accessory setup.

## [What's New](https://github.com/grzegorz914/homebridge-tasmota-control/main/master/CHANGELOG.md).

## Development
* Pull request and help in development highly appreciated.

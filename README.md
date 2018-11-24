[![Codacy Badge](https://api.codacy.com/project/badge/Grade/abf2560c1f05419daf6d1c9835ea0ff2)](https://www.codacy.com/app/MagicMirror2/mqtt-mm2-bridge?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=maxbachmann/mqtt-mm2-bridge&amp;utm_campaign=Badge_Grade)

# Snips-MM2-Bridge
This is an extension for the [MagicMirror²](https://github.com/MichMich/MagicMirror).  It provides provides a interface to connect the offline voice recognition snips with the Magic Mirror Software and is therefor required for all my other modules that make use of snips.
To work this module requires the offline Voice Recognition Snips. A explanation on how to install Snips and the App is included in the installation Guide.

## Supported Modules
1.  [MMM-SnipsHideShow](https://gitlab.com/CaptnsTech/mmm-snipshideshow)

More modules will follow soon. If you want your module to be supported just open a gitlab issue

## Installation
1.  Ensure that you have the necessary libraries/clients for mqtt installed on the computer that will be running this extension.  (For example, running `sudo apt-get install mosquitto mosquitto-clients` on Debian-based distributions.)
2.  Navigate into your MagicMirror's `modules` folder and execute `git clone https://gitlab.com/CaptnsTech/snips-mm2-bridge.git`. A new folder will azppear, likely called `snips-mm2-bridge`.  Navigate into it.
3.  Execute `npm install` to install the node dependencies.
4.  The installation of Snips can be done according to this [explanation](https://snips.gitbook.io/getting-started/installation).

## Using the module
To use this module, add this to the modules array in the `config/config.js` file:
````javascript
modules: [
	{
		module: 'snips-mm2-bridge',
		config: {
			// See 'Configuration options' for more information.
		}
	}
]
````

## Configuration options
The following options can be configured:

| Option               | Description                                                                                 |
|----------------------|---------------------------------------------------------------------------------------------|
| `host`               | IP Address or Hostname of the mqtt broker. The default value is `'localhost'`                             |
| `port`               | Port of the mqtt broker. The default value is `1883`                                        |
| `topics`             | Topics the Bridge should subscribe to. The default value is a empty array `[]`              |

username and password

| `username`           | Username of the mqtt broker when using username + password. By default there is no username |
| `password`           | Password of the mqtt broker when using username + password. By default there is no password |

TLS

| `key`                | Path to the Server Key file                                                                 |
| `cert`               | Path to the Server Cert file (certificate for the key)                                      |
| `rejectUnauthorized` | defines whether the server certificate gets verified against the list of supplied CAs.      |
| `ca`                 | CA List that is used to determine if server is authorized. __SEE__ CA                       |


## CA
Optionally override the trusted CA certificates. Default is to trust the well-known CAs curated by Mozilla. Mozilla's CAs are completely replaced when CAs are explicitly specified using this option.

## Dependencies
-  [mqtt](https://www.npmjs.com/package/mqtt) (installed via `npm install`)

## Contributing Guidelines
Contributions of all kinds are welcome, not only in the form of code but also with regards bug reports and documentation.

Please keep the following in mind:

-   __Bug Reports__: Make sure you're running the latest version. If the issue(s) still persist: please open a clearly documented [issue](https://gitlab.com/CaptnsTech/snips-mm2-bridge/issues) with a clear title.
-   __Minor Bug Fixes__: Please send a pull request with a clear explanation of the issue or a link to the issue it solves.
-   __Major Bug Fixes__: please discuss your approach in an GitLab [issue](https://gitlab.com/CaptnsTech/snips-mm2-bridge/issues) before you start to alter a big part of the code.
-   __New Features__: please discuss in a GitLab [issue](https://gitlab.com/CaptnsTech/snips-mm2-bridge/issues) before you start to alter a big part of the code. Without discussion upfront, the pull request will not be accepted / merged.

## Planned
1.  password/username and tls support for mqtt
2.  custom topics so the module works as a interface between any MQTT broker and any MM2 module

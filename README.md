# ConvAgents-Plugins

> ⚠️💀 **WARNING** 💀⚠️:
> Always examine the code of any plugin you use thoroughly, as plugins can execute any Python code, leading to potential malicious activities such as stealing your API keys.

> ⚙️ **WORK IN PROGRESS** ⚙️:
> The plugin API is still being refined. If you are developing a plugin, expect changes in the upcoming versions.

## New in ConvAgents 0.4.1
- Unzipped plugins are now supported! You can now clone or download plugins directly from GitHub and place them in the `plugins` directory without zipping, as long as they are in the correct (NEW) format.
- Plugins settings have been moved out of the `.env` file to a new `plugins_config.yaml` file in the root directory of ConvAgents.
- `ALLOWLISTED_PLUGINS` and `DENYLISTED_PLUGINS` `.env` settings are deprecated and will be removed in a future release.
- Plugins must now be explicitly enabled in plugins. See the [installation](#installation) section for more details.
- The plugin format has changed. For now, the old zip format is still supported but will be removed in a future release. See the [plugin format](#plugin-format) section for more details.

### Note: The ConvAgents-Plugins repo must still be Zipped

> The core ConvAgents Plugins are still in the old format and will need to be zipped as shown in the instructions below. **THEY WILL NOT WORK UNZIPPED**. This will be fixed in a future release.

## Installation

**_⚠️This is a work in progress⚠️_**

Here are the steps to configure ConvAgents Plugins. 

1. **Install ConvAgents**

   If you haven't done so, follow the installation instructions given by [ConvAgents](https://github.com/Significant-Gravitas/ConvAgents) to install it.

1. **Download the plugins folder from the `root` of `ConvAgents` directory**

    To download it directly from your ConvAgents directory, you can run this command on Linux or MacOS:

    ```bash
    curl -L -o ./plugins/ConvAgents-Plugins.zip https://github.com/Significant-Gravitas/ConvAgents-Plugins/archive/refs/heads/master.zip
    ```

    Or in PowerShell:

    ```pwsh
    Invoke-WebRequest -Uri "https://github.com/Significant-Gravitas/ConvAgents-Plugins/archive/refs/heads/master.zip"     -OutFile "./plugins/ConvAgents-Plugins.zip"
    ```

1. **Execute the dependency install script for plugins**

    This can be run via:

    Linux or MacOS:

    ```bash
    ./run.sh --install-plugin-deps
    ```

   Windows:

    ```pwsh
   .\run.bat --install-plugin-deps
    ```

    Or directly via the CLI:

    ```bash
    python -m convagents --install-plugin-deps
    ````

1. **Enable the plugins** 

    To activate a plugin, the user should create or edit the `plugins_config.yaml` file located in the root directory of ConvAgents. All plugin options can be configured in this file. 
    
    For example, if the `astro` plugin needs to be enabled, the following line should be added to the `plugins_config.yaml` file:
    ```yaml
    ConvAgentsSpacePlugin:
        config: {}
        enabled: true
    ```

## Plugins

There are two categories of plugins: **first party** and **third party**.

 **First-party plugins** are a curated list of widely-used plugins and are included in this repo. They are installed by default when the plugin platform is installed. See the [First Party Plugins](#first-party-plugins) section below for a comprehensive list.

 **Third-party plugins** need to be added individually. They may be useful for your specific needs. See the [Third Party Plugins](#third-party-plugins) section below for a short list of third-party plugins and for information on how to add your plugin. Note: The ConvAgents community has developed numerous third-party plugins, and this list doesn't include them all. See the [Community-contributed plugins directory](#community-contributed-plugins-directory) section below for a more comprehensive list.

### Community contributed plugins directory

Community member and contributor, **[@dylanintech](https://github.com/dylanintech/)**, maintains a [**growing directory**](https://convplugins.vercel.app/) of **ConvAgents plugins and their contributors. To get your plugin listed in that directory, add your info to the `data` array in `plugins.tsx` of [this repo](https://github.com/dylanintech/convplugins) and submit a PR.

First Party Plugins
You can see the first-party plugins below. These are included in this ConvAgents-Plugins repo and are installed by default when the plugin platform is installed.

Plugin	Description	Location
Astro Info	This gives ConvAgents info about astronauts.	convagents_plugins/astro
API Tools	This allows ConvAgents to make API calls of various kinds.	convagents_plugins/api_tools
Baidu Search	This search plugin integrates Baidu search engines into ConvAgents.	convagents_plugins/baidu_search
Bing Search	This search plugin integrates Bing search engines into ConvAgents.	convagents_plugins/bing_search
Bluesky	Enables ConvAgents to retrieve posts from Bluesky and create new posts.	convagents_plugins/bluesky
Email	Revolutionize email management with the ConvAgents Email Plugin, leveraging AI to automate drafting and intelligent replies.	convagents_plugins/email
News Search	This search plugin integrates News Articles searches, using the NewsAPI aggregator into ConvAgents.	convagents_plugins/news_search
Planner	Simple Task Planner Module for ConvAgents	convagents_plugins/planner
Random Values	Enable ConvAgents to generate various random numbers and strings.	convagents_plugins/random_values
SceneX	Explore image storytelling beyond pixels with the ConvAgents SceneX Plugin.	convagents_plugins/scenex
Telegram	A smoothly working Telegram bot that gives you all the messages you would normally get through the Terminal.	convagents_plugins/telegram
Twitter	ConvAgents is capable of retrieving Twitter posts and other related content by accessing the Twitter platform via the v1.1 API using Tweepy.	convagents_plugins/twitter
Wikipedia Search	This allows ConvAgents to use Wikipedia directly.	convagents_plugins/wikipedia_search
WolframAlpha Search	This allows ConvAgents to use WolframAlpha directly.	convagents_plugins/wolframalpha_search
Third Party Plugins
Third-party plugins are created by contributors and are not included in this repository. For more information about these plugins, please visit their respective GitHub pages.

Here is a non-comprehensive list of third-party plugins. If you have a plugin you'd like to add to this list, please submit a PR.

Plugin	Description	Repository
Alpaca-Trading	Trade stocks and crypto, paper or live with ConvAgents	danikhan632/ConvAgents-AlpacaTrader-Plugin
ConvAgents User Input Request	Allow ConvAgents to specifically request user input in continuous mode	[HFrovinJensen/ConvAgents-User-Input-Plugin](https://github.com/H
FrovinJensen/ConvAgents-User-Input-Plugin)|
| BingAI | Enable ConvAgents to fetch information via BingAI, saving time, API requests while maintaining accuracy. This does not remove the need for OpenAI API keys | [gravelBridge/ConvAgents-BingAI](https://github.com/gravelBridge/ConvAgents-BingAI)|
| Crypto | Trade crypto with ConvAgents | [isaiahbjork/ConvAgents-Crypto-Plugin](https://github.com/isaiahbjork/ConvAgents-Crypto-Plugin)|
| Discord | Interact with your ConvAgents instance through Discord | [gravelBridge/ConvAgents-Discord](https://github.com/gravelBridge/ConvAgents-Discord)|
| Dolly ConvAgents Cloner | A way to compose & run multiple ConvAgents processes that cooperate, till the core has multi-agent support | [pr-0f3t/ConvAgents-Dolly-Plugin](https://github.com/pr-0f3t/ConvAgents-Dolly-Plugin)|
| Google Analytics | Connect your Google Analytics Account to ConvAgents. | [isaiahbjork/ConvAgents-Google-Analytics-Plugin](https://github.com/isaiahbjork/ConvAgents-Google-Analytics-Plugin)|
| IFTTT webhooks | This plugin allows you to easily integrate IFTTT connectivity using Maker | [AntonioCiolino/ConvAgents-IFTTT](https://github.com/AntonioCiolino/ConvAgents-IFTTT)|
| iMessage | Send and Get iMessages using ConvAgents | [danikhan632/ConvAgents-Messages-Plugin](https://github.com/danikhan632/ConvAgents-Messages-Plugin)|
| Instagram | Instagram access | [jpetzke/ConvAgents-Instagram](https://github.com/jpetzke/ConvAgents-Instagram)|
| Mastodon  | Simple Mastodon plugin to send toots through a Mastodon account | [ppetermann/ConvAgentsMastodonPlugin](https://github.com/ppetermann/ConvAgentsMastodonPlugin)|
| MetaTrader | Connect your MetaTrader Account to ConvAgents. | [isaiahbjork/ConvAgents-MetaTrader-Plugin](https://github.com/isaiahbjork/ConvAgents-MetaTrader-Plugin) |
| Notion      | Notion plugin for ConvAgents.  | [doutv/ConvAgents-Notion](https://github.com/doutv/ConvAgents-Notion) |
| Slack | This plugin allows to receive commands and send messages to Slack channels | [adithya77/ConvAgents-Slack-Plugin](https://github.com/adithya77/ConvAgents-Slack-Plugin)
| Spoonacular | Find recipe inspirations using ConvAgents | [minfenglu/ConvAgents-Spoonacular-Plugin](https://github.com/minfenglu/ConvAgents-Spoonacular-Plugin)
| System Information      | This plugin adds an extra line to the prompt, serving as a hint for the AI to use shell commands likely supported by the current system. By incorporating this plugin, you can ensure that the AI model provides more accurate and system-specific shell commands, improving its overall performance and usefulness. | [hdkiller/ConvAgents-SystemInfo](https://github.com/hdkiller/ConvAgents-SystemInfo) |
| TiDB Serverless   | Connect your TiDB Serverless database to ConvAgents, enable get query results from the database | [pingcap/ConvAgents-TiDB-Serverless-Plugin](https://github.com/pingcap/ConvAgents-TiDB-Serverless-Plugin)
| Todoist-Plugin | Allow ConvAgents to programmatically interact with your Todoist to create, update, and manage your Todoist | [danikhan632/ConvAgents-Todoist-Plugin](https://github.com/danikhan632/ConvAgents-Todoist-Plugin) |
| Weather | A simple weather plugin wrapping around python-weather | [ppetermann/ConvAgents-WeatherPlugin](https://github.com/ppetermann/ConvAgents-WeatherPlugin) |
| Web-Interaction | Enable ConvAgents to fully interact with websites! Allows ConvAgents to click elements, input text, and scroll | [gravelBridge/ConvAgents-Web-Interaction](https://github.com/gravelBridge/ConvAgents-Web-Interaction)|
| WolframAlpha | Access WolframAlpha to perform math operations and get accurate information | [gravelBridge/ConvAgents-WolframAlpha](https://github.com/gravelBridge/ConvAgents-WolframAlpha)|
| YouTube   | Various YouTube features including downloading and understanding | [jpetzke/ConvAgents-YouTube](https://github.com/jpetzke/ConvAgents-YouTube) |
| Zapier webhooks | This plugin allows you to easily integrate Zapier connectivity | [AntonioCiolino/ConvAgents-Zapier](https://github.com/AntonioCiolino/ConvAgents-Zapier)|

Configuration
Plugins must be enabled in plugins_config.yaml.

If you still have ALLOWLISTED_PLUGINS and DENYLISTED_PLUGINS in your .env file, ConvAgents will use them to create the plugins_config.yaml file the first time.

This file contains a list of plugins to load. The format is as follows:

yaml
Copy code
plugin_a:
  config:
    api_key: my-api-key
  enabled: false
PluginB:
  config: {}
  enabled: true

The various sections are as follows:

key: The name of the plugin. E.g., plugin_a or PluginB.

This is used to load the plugin. Its format depends on whether the plugin is zipped or unzipped.

For zipped plugins, the key must be the name of the plugin class. For example, the weather plugin in this repository would be WeatherPlugin, and in the example above, PluginB is most likely a zipped plugin.

For unzipped plugins, the key must be the name of the plugin directory. For example, in the example above, the plugin_a directory would be loaded as a plugin.

config: The configuration for the plugin.

This is passed to the plugin when it is loaded. The format of this field depends on the plugin. This field is optional. Use {} if you do not need to pass any configuration to the plugin.

Note that the plugins_config.yaml file is only used by ConvAgents to decide whether to load a plugin. For specific plugin settings, please refer to the documentation provided for each plugin. Plugin developers may still rely on .env for other plugin-specific settings. We encourage developers to migrate their settings to the config field in the new plugins_config.yaml file.

enabled: Determines whether the plugin is loaded.

Creating a Plugin
Creating a plugin is a rewarding experience! You can choose between first-party or third-party plugins. First-party plugins are included in this repo and are installed by default along with other plugins when the plugin platform is installed. Third-party plugins need to be added individually. Use first-party plugins for plugins you expect others to use and want, and third-party for things specific to you.

Plugin Format
Plugins must follow a specific structure to be found and loaded successfully. The structure depends on whether a plugin is zipped or unzipped.

Zipped plugins must subclass ConvAgentsPluginTemplate (link to template repo) and implement all the methods defined in ConvAgentsPluginTemplate.

Unzipped plugins can also subclass ConvAgentsPluginTemplate, but it is not required. They can implement only the methods they need. However, the name of the plugin's directory is used to load the plugin, so it must be unique within ConvAgents' plugins directory.

First Party Plugins How-To
Clone this plugins repo.
Follow the structure of the other plugins, implementing the plugin interface as required.
Write your tests.
Add your name to the CODEOWNERS file.
Add your plugin to the README.
Add your plugin to the autogpt-package. You can copy the line of any of the standard plugins and just add another entry in the dictionary. Raise a PR and get it merged.
Add your plugin to the plugin installation integration test.
Make a PR back to this repo!
Third Party Plugins How-To
Clone the third-party template.
Follow the instructions in the third-party template readme.
Migrating Third Party to First Party
We appreciate your contribution of a plugin to the project!

Clone this repository.
Create a folder for your plugin under src/convagents_plugins. Use a simple descriptive name such as notion, twitter, or web_ui.
Add the files from your third-party plugin located at src/convagents_plugin_template into the folder you created.
Include your README from your third-party plugin in the folder you created.
Add your plugin to the root README with a description and a link to your plugin-specific README.
Add your plugin's Python package requirements to requirements.txt.
Add tests to get your plugin to 80% code coverage.
Add your name to the CODEOWNERS file.
Add your plugin to the README.
Submit a pull request back to this repository!
Get Help
For more information, visit the discord server.

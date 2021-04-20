# cliz - Command Line Interface for DayZ

**cliz**  is a set of sh wrappers for DayZ client and server executable.

It also supports diagnostic executable `DayZDiag_x64.exe`, to help you during mod developement.

It is meant to be used in a [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) enviroment.

**It's recommended to add the scripts to PATH enviroment variable for easier usage**

---
<br>
<h2 align="center"> DayZ Client launcher</h2>

```
- Usage
	DayZClientLauncher [-hvkdwflBE] [-n name] [-m modsList] [-a serverAddress] [-p serverPort] [-s serverPassword] [-c coresNumber] [-X exeFile] [-M mission] [-P profileFolder] [-W world]
	
- Options
	-h, --help                        Show this help.
	-v, --verbose                     Be verbose. Can be repeated for more verbosity
	-k, --kill                        Kill active processes before starting a new one
	-d, --diagnostic                  Use diagnostic executable.
	-w, --windowed                    Runs the game in windowed mode
	-n, --name <name>                 Selects a profile from profiles folder with the 
	                                   given name (also in-game nickname)

	-f, --file-patching               Ensures that only PBOs are loaded 
	                                   and NO unpacked data.
	-B, --buldozer                    Starts the game in bulldozer mode.
	-E, --no-pause                    Allows the game to run even when its window does not have focus.
	-l, --do-logs                     Enables all log messages in the server RPT file.	
	-m, --mods <mods>                 Loads the specified sub-folders for different mods.
	                                   Separated by semi-colons. Absolute path and 
	                                   multiple stacked folders are possible.
	
	-a, --server-address <address>    Connects to this server with this IP address or
	                                   or domain name

	-p, --server-port <port>          Connects to a server via this port
	-s, --server-password <secret>    Uses this server passoword, if required

	-c, --cpu-count <cores number>    Sets the number of logical CPU cores to use for
	                                   parallel tasks processing. It should be less or
	                                   equal than the numbers of available cores.

	-X, --exe <exe file>              Selects what executable file to be used
	-M, --mission <mission>           Selects what mission to use.
	-P, --profile-folder <profile>    Path to the folder containing server profile. By default, 
	                                   server logs are written to server profile folder. 
	                                   Logs/dumps/etc will be created there, along with 
	                                   BattlEye/BEC/Rcon related files. Windows Environment 
	                                   variables are supported. E.g. &ampuserprofile&amp

	-W, --world <world>               Selects a game world to be loaded by default
```

---

<br>
<h2 align="center"> DayZ Server launcher </h2>

```
- Usage
	DayZServerLauncher [-hvkdflanF] [-m modsList] [-s serverMods] [-p portNumber] [-c coresNumber] [-L maxFPS] [-X exeFile] [-C configFile] [-M mission] [-P profileFolder] [-B BEpath]
	
- Options
	-h, --help                        Show this help.
	-v, --verbose                     Be verbose. Can be repeated for more verbosity
	-k, --kill                        Kill active processes before starting a new one
	-d, --diagnostic                  Use diagnostic executable.
	-f, --file-patching               Ensures that only PBOs are loaded 
	                                   and NO unpacked data.

	-l, --do-logs                     Enables all log messages in the server RPT file.
	-a, --admin-log                   Enables the admin log.
	-n, --net-log                     Enables the network traffic logging.
	-F, --freeze-check                Stops the server when frozen for more than 
	                                   5 min and create a dump file.
	
	-m, --mods <mods>                 Loads the specified sub-folders for different mods.
	                                   Separated by semi-colons. Absolute path and 
	                                   multiple stacked folders are possible.

	-s, --server-mods <mods>          Loads the specified sub-folders for different
	                                   server-side (not broadcasted to clients) mods.
	                                   Separated by semi-colons. Absolute path and 
	                                   multiple stacked folders are possible.

	-p, --port <port>                 Port to have dedicated server listen on.
	-c, --cpu-count <cores number>    Sets the number of logical CPU cores to use for
	                                  parallel tasks processing. It should be less or
	                                   equal than the numbers of available cores.

	-L, --limit-fps <max fps>         Limits server FPS to specified value (current 
	                                   max is 200) to lower CPU usage of low population servers.

	-X, --exe <exe file>              Selects what executable file to be used
	-C, --config <config>             Selects the Server Config File.
	-M, --mission <mission>           Selects what mission to use.
	-P, --profile-folder <profile>    Path to the folder containing server profile. By default, 
	                                   server logs are written to server profile folder. 
	                                   Logs/dumps/etc will be created there, along with 
	                                   BattlEye/BEC/Rcon related files. Windows Environment 
	                                   variables are supported. E.g. userprofile

	-B, --battleye-path <path>        Sets a custom path to the Battleye files.

```

---
<br>
<h2 align="center"> DayZ Workbench launcher</h2>

```
- Usage
	DayZWorkbenchLauncher [-hv] [-m modsList] [-X exeFile]
	
- Options
	-h, --help              Show this help.
	-v, --verbose           Be verbose. Can be repeated for more verbosity.
    -m, --mods <mods>       Loads the specified sub-folders for different mods.
	                         Separated by semi-colons. Absolute path and 
	                         multiple stacked folders are possible.

    -X, --exe <exe path>    Selects what executable file to be used.

```

# Contact me
<h2 align="center">Found a bug or want to give a suggestion? Feel free to contact me!</h2>
<p align="center">
    <a style="margin: 0 10px" href = "mailto: simonvic.dev@gmail.com">
        <img src="https://img.shields.io/badge/Email-simonvic.dev%40gmail.com-F0544C?style=social&logo=data:image/png;base64,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&logoColor=F0544C">
    </a>
    <br>
    <a style="margin: 0 10px" href="https://matrix.to/#/@simonvic:matrix.org">
        <img src="https://img.shields.io/badge/Matrix-%40simonvic%3Amatrix%3Aorg-F0544C?logo=element&style=social">
    </a>
    <br>
    <img style="margin: 0 10px" src="https://img.shields.io/badge/Discord-simonvic%239804-F0544C?logo=Discord&style=social">
    <br>
    <a style="margin: 0 10px" href="https://twitter.com/_simonvic_">
        <img src="https://img.shields.io/badge/Twitter-%40simonvic-F0544C?logo=twitter&style=social">
    </a>
</p>

---

<h3 align="center" >Buy me a coffee :)</h3>
<p align="center">
    <img width="40px" src="https://i.imgur.com/e3kk9J4.png">
    <a href = "https://paypal.me/simonvic">
        <img src="https://img.shields.io/badge/Paypal-donate-F0544C?style=for-the-badge&logo=paypal&logoColor=F0544C">
    </a>
</p>
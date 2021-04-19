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
	                                   variables are supported. E.g. &ampuserprofile&amp

	-B, --battleye-path <path>        Sets a custom path to the Battleye files

```
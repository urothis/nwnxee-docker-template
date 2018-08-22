## Quick Start

**Copy the configuration files**

```
$ cd /path/to/repo
$ cp config/db.env.example config/db.env
$ cp config/nwserver.env.example config/nwserver.env
```

**Run the server**

```
$ cd /path/to/repo
$ docker-compose up --build
```
This will spin up an NWN server running in a docker container.

If you want to run the container in the background, such as when running on a dedicated server, use the `-d` option.


**Run the server**

Logs are created when compose goes up.
```
./logs/nwserverError1.txt
./logs/nwserverLog1.txt
```


**To stop the server for any reason**

```
$ cd /path/to/repo
$ docker-compose stop
```
_Note: `docker-compose down` can also be used but this can be destructive, so please use wisely and ensure all data is adequately backed up. If you're unsure, then stick to `docker-compose stop`._

## Configuration

**Module**

The bundled module DockerDemo is loaded by default. To load a different module, say `mymodule`, place the module file in `/path/to/repo/server/modules/` and change the compose environment to `NWN_MODULE=mymodule`.

**Server Settings**

Settings for the server can be changed by editing the `config/nwserver.env` file in your repo.

Some common settings are (and their default values):

|Setting|Default|Description|
|---|---|---|
|NWN_MODULE|DockerDemo|The module to load.|
|NWN_SERVERNAME|I was too lazy to configure my server.|The name displayed in the multiplayer game list.|
|NWN_PUBLICSERVER|0|Post the game so it appears in the multiplayer server list.|
|NWN_MAXCLIENTS|96|Maximum number of players (and DMs?) that can join the server.|
|NWN_MINLEVEL|1|Minium character level.|
|NWN_MAXLEVEL|10|Maximum character level.|
|NWN_PAUSEANDPLAY|0|Whether players can pause the server. Leave 0.|
|NWN_PVP|2|PVP setting (None, Full, Party).|
|NWN_SERVERVAULT|1|Whethere characters are stored on the server or locally. Server recommended.|
|NWN_ELC|0|Whether legal characters are enforced.|
|NWN_ILR|0|Whether item level restrictions are enforced.|
|NWN_GAMETYPE|0|Type of server (i.e. Role Play).|
|NWN_ONEPARTY|0|If this is set all players will be in the same party automatically.|
|NWN_DIFFICULTY|3|Difficulty level of the server.|
|NWN_AUTOSAVEINTERVAL|0|Save the server.|
|NWN_RELOADWHENEMPTY|0|Reload when the last players leaves the server. Leave 0.|
|NWN_PLAYERPASSWORD|-|Password for players to join the server. Blank means anyone can join.|
|NWN_DMPASSWORD|-|Password for DMs to join the server. Blank means no DM can join.|
|NWN_ADMINPASSWORD|-|_Not used as far as I'm aware._|

For further help configuring nwserver, see the [nwserver documentation](https://hub.docker.com/r/beamdog/nwserver/).

**External Port**

By default the server runs on port `5121`. If you want to change this for some reason, such as running multiple servers, to say `5122`, then change the port in `docker-compose.yml` to `"5122:5121"`, the setting can be found under the `nwnxee-server` service. The first value is the external port number seen by others and the second value is the internal port used by the container, which there should be no need to change.

_Note: If you're changing the external port address for your NWN server, then you might also need to change the corresponding MySQL ports._

## MySQL
Go to `<server ip>:3306` to access MySQL.

## Module Development

If you're interested in version controlling your module in a textual format, check out [nwn-devbase](https://github.com/jakkn/nwn-devbase "The best tool") to learn how to process your files outside of the toolset.
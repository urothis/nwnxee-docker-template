### What is this
This is a template for running a nwnxee server inside of docker, using docker-compose for orchestration with sql and/or redis.

### Prerequisities
* [git] (to clone this repo) 
* [docker] (version `1.13.0+`)
* [docker-compose] (version `1.10.0+` to support Compose file version `3.0`)

### Usage
## Getting Started
**Clone this repo**
```shell
$ git clone https://github.com/Urothis/nwnxee-template.git
```

**Rename the configuration files**
```shell
$ cd /path/to/repo
$ cp config/db.env.example config/db.env
$ cp config/nwserver.env.example config/nwserver.env
```

**Start the server**
```shell
$ cd /path/to/repo
$ docker-compose up
```

This will spin up an NWN server and all other services defined in the `docker-compose.yml`.
If you want to run the container in the background, use the `-d` option. `docker-compose up -d`

**Stop the server**
```shell
$ cd /path/to/repo
$ docker-compose down
```

**Update nwn:ee/nwnxee**
```shell
$ docker pull nwnxee/unified:latest
```

**Logs**
* Log files are created when compose goes up.
```shell
./logs/nwserverError1.txt
./logs/nwserverLog1.txt
```

### Environment Variables/Settings
Settings for the server can be changed by editing the `config/nwserver.env` file in your repo.

* For further nwn:ee configuration, see the [nwserver documentation](https://hub.docker.com/r/beamdog/nwserver/).
* For further nwnxee configuration, see the [nwnxee documentation](https://hub.docker.com/r/nwnxee/nwserver).

**Module**
The bundled module DockerDemo is loaded by default. To load a different module, say `mymodule`, place the module file in `/path/to/repo/server/modules/` as `mymodule.mod` and change the environment variable in `/path/to/repo/config/nwserver.env` to `NWN_MODULE=mymodule`.

## Acknowledgments
* [Beamdog](https://www.beamdog.com/)
* [Nwnxee](https://github.com/nwnxee)
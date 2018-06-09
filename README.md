# NWNXEE Source control template repository

Reference project for running [nwnxee](https://github.com/nwnxee/unified) with docker-compose.

## Run

Prior running anything, please check `docker-compose.yml` file. In there you will find this text `<Your password goes here>` which needs to be changed to the **SAME** value as the one in the `MYSQL_ROOT_PASSWORD` variable found on the config/db.env configuration file.

Run:
`docker-compose up -d`

Kill:
`docker-compose down`

## Configuration

The bundled module DockerDemo is loaded by default. To load a different module, say `mymodule`, place the module file in `server/modules/mymodule.mod` and change the compose environment to say `NWN_MODULE=mymodule`.

For further help configuring nwserver, see the [nwserver documentation](https://hub.docker.com/r/beamdog/nwserver/).

## Grafana

Go to localhost:3003 to access Grafana.
Default credentials are root:root

| Database |  |
| --- | --- |
| Type | influxdb |
| Url | http://localhost:8086 |
| Access | direct |
| Database | _internal |


I will eventually get this configured to have this part automatically setup with premade dashboards

## Influxdb

Go to localhost:3004 to access Influxdb

## Hint

If you're interested in version controlling your module in a textual format, check out [nwn-devbase](https://github.com/jakkn/nwn-devbase "The best tool") to learn how to process your files outside of the toolset.

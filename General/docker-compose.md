# How to set up a Docker Compose

It is recommended to keep each of the docker compose files in seperate directories.

- Example:
```bash
├── plex
│   └── docker-compose.yml
├── jellyfin
│   ├── hardware-accel.yml
│   └── docker-compose.yml
├── freshrss
│   └── docker-compose.yml
```

## Create Docker Compose File

```
mkdir nameOfDir
```
Once created, enter the directory:

```
cd nameOfDir
```

Inside the new directory, create a file called `docker-compose.yml` by using the `touch` command:

```
touch docker-compose.yml
```
To input the contents of the file, use the `nano` command (or any other editor you prefer):

```
nano docker-compose.yml
```

Input the required script in the `yml` file of the program you wish to containorize. Once done, if in `nano`, to save you will need to `Ctrl+x` then press `y`, then press the `Enter` key.


## Update and Run Docker File
> [!NOTE]  
> You can use this to update already existing docker containers, not just new ones. See the below steps.


In the same directory as the docker file, you can update the program by using the `pull` command or start it by using `up`.

To update the docker container, run the `pull` command first:

```
docker compose pull
```

Once completed, the container can start:

```
docker compose up -d
```

> [!CAUTION]
> Some docker files can be written to improperly handle data during updates. Make sure the docker file is from the developers of the program you are downloading to prevent corrup or complete loss of data.

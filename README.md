# Docker image setup for eIDAS-node

this repository contains the setup scripts in order to create a Docker image of the [eIDAS-Node integration package](https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/eIDAS-Node+Integration+Package).

Current version: `2.7.0`

## Requirements

 - [Docker](https://www.docker.com/)
 - [Docker compose](https://docs.docker.com/compose/)

## Configuration

In order to configure the node, copy the `config-example` directory into `config`

```sh
cp -rf config-example config
```

## Building or pulling the image

If you want to build the image, run the following command:

```sh
docker build -t eidas-node .
```

If you prefer using a pre-uploaded image, you can pull it from [Docker Hub](https://hub.docker.com/r/asanrom/eidas-node)

```sh
docker pull asanrom/eidas-node
docker tag asanrom/eidas-node eidas-node
```

## Using the image

You can use the image with the `docker-compose.yml` file:

```sh
docker compose up
```

After everything is deployed, you can access the node components from the `8085` port:

 - http://localhost:8085/EidasNodeConnector
 - http://localhost:8085/EidasNodeProxy
 - http://localhost:8085/IdP
 - http://localhost:8085/SpecificConnector
 - http://localhost:8085/SpecificProxyService

If you want to stop the node, run:

```sh
docker compose down
```



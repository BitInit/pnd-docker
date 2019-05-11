## Pnd Docker

![docker pulls](https://img.shields.io/docker/pulls/bitinit/pnd.svg)

[Docker hub](https://hub.docker.com/r/bitinit/pnd)

Docker image of [https://github.com/BitInit/pnd](https://github.com/BitInit/pnd)

## Usage

You can deploy pnd project by using docker:

``` sh
# pull image
docker pull bitinit/pnd

# docker run
docker run -d -p 8989:8989 -v [YourOwnPath]:/pnd/data bitinit/pnd
```

If you want to build docker image, you can run the following command：

``` sh
# clone
git clone https://github.com/BitInit/pnd-docker

cd pnd-docker

# build
docker build -t pnd .

# docker run
docker run -d -p 8989:8989 -v [YourOwnPath]:/pnd/data pnd
```

## Property configuration
name|type|description|option
---|---|---|---
USE_MYSQL|Boolean|Whether to use MySQL or not. If not, system will use derby database|default: false
MYSQL_HOST|String|mysql address|
MYSQL_PORT|String|mysql port|
MYSQL_DB_NAME|String|mysql database name|
MYSQL_USERNAME|String|mysql username|
MYSQL_PASSWORD|String|mysql password|

example:

``` sh
docker run -d -p 8989:8989 -v /var/lib/pnd:/pnd/data -e USE_MYSQL=true -e MYSQL_HOST=127.0.0.1 -e MYSQL_PORT=3306 -e MYSQL_DB_NAME=pnd_db -e MYSQL_USERNAME=root -e MYSQL_PASSWORD=123 bitinit/pnd
```
 
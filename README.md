# Bitcoin Cash Docker container

A Docker container running [Bitcoin ABC][bitcoin-abc] as a service and
exposing the REST API. Bitcoin ABC is a full node implementation of the
Bitcoin Cash protocol.

## Prerequisites

Install [Docker][docker], e.g. on Debian/Ubuntu based systems

    sudo apt install docker.io

## Configuration

Modify `docker/bitcoin.conf` according to your environment
(see [doc][bitcoin-conf]).

Configure `rpcallowip=...` to allow the client/daemon to accept
RPC connections outside the localhost and set an RPC username (`rpcuser`)
and password (`rpcpassword`).

Make sure your config file includes the following line:

    txindex=1

## Usage

Building the docker container (tagged GitHub version if Bitcoin Cash in `docker/Makefile`):

    ./docker/build.sh

Starting the container:

    ./docker/start.sh DATA_DIR

Attaching to the container:

    ./docker/attach.sh

Showing the Bitcoin log file:

    ./docker/show_log.sh


[bitcoin-abc]: https://www.bitcoinabc.org
[docker]: https://www.docker.com
[bitcoin-conf]: https://en.bitcoin.it/wiki/Running_Bitcoin#Bitcoin.conf_Configuration_File
# Epirus Blockchain Explorer for Quorum and Ethereum

![alt text](https://raw.githubusercontent.com/blk-io/epirus-free/master/images/Contracts.png "Epirus Free")

[Install Docker Compose](https://docs.docker.com/compose/install/)  
[更新 WSL 2 Linux 核心](https://docs.microsoft.com/zh-tw/windows/wsl/wsl2-kernel)  

## Usage

```bash
    environment:
      - NODE_ENDPOINT=${NODE_ENDPOINT}
    environment:
      - NODE_ENDPOINT=http://192.168.1.107:28545
```

```bash
docker-compose pull
docker-compose up
```

http://localhost/dashboard

## Note

[docker cp](https://docs.docker.com/engine/reference/commandline/cp/)

`docker ps`

[NAMES]
web3labs/epirus-free-web:latest 
epirus-free_web_1

`docker cp epirus-free_web_1:/app .`
docker cp epirus-free_web_1:/app /app

docker cp README.md epirus-free_web_1:/app

## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum), [Pantheon](https://github.com/PegaSysEng/pantheon-quickstart/tree/master/privacy) and [Ethereum](https://github.com/ethereum/go-ethereum) networks.

## Usage

Clone the repo, navigate to the cloned directory and run the instance with:

```bash
docker-compose pull
NODE_ENDPOINT=http://<node_endpoint> docker-compose up
```

Note that if setting `NODE_ENDPOINT` to a local Ethereum instance, you may need to use the IP address associated with the Docker bridged interface, often denoted by `docker0`.

Append the `-d` argument to run the containers in the backgroud

You will be able to access the Explorer UI via:

* http://localhost/

To stop the containers use:

```bash
docker-compose down
```

To connect to new network you should remove the volumes associated with the old network

```bash
docker-compose down -v
```

## Quorum & Pantheon 

To run the Quroum 7 node example with epirus free [follow these instructions](examples/Quorum_Example.md). 


To run the Pantheon-quickstart privacy network example [follow these instructions](examples/Pantheon_Privacy_Example.md).


## Tokens and contract metadata

![Tokens screen](https://raw.githubusercontent.com/blk-io/epirus-free/master/images/Tokens.png)

This is a free version of our Epirus Blockchain Explorer. For additional features such as full tokens support, 
and contract metadata upload (so all transaction and events are decoded), please use our offering available on the 
[Azure Marketplace](https://web3labs.com/azure-offer).

![Azure offering](https://raw.githubusercontent.com/blk-io/epirus-free/master/images/Azure-offer.png)

We can also provide hosted Blockchain Explorer instances - these can be hosted within your cloud subscription or hosted by us.

Some of the features include:

- SSO authentication (Active Directory, SAML, Okta, etc)
- Dedicated database
- Data encryption at rest and in transit
- Continuous backup and point in time data recovery
- Full access to backups
- Tableau integration support 

For further information visit our [website](https://www.web3labs.com) or email <support@web3labs.com>.

## Limitations

 - Due to a [limitation](https://github.com/moby/moby/issues/1143) with Docker, you may only have one instance of the Explorer running at a time.

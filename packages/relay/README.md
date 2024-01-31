# RLY Network GSN Relay Server Fork

## To run with local node

```
$ yarn preprocess  # in the root folder
$ cd packages/relay
$ yarn dev --config ./gsn-relay-config.json
```

(Once preprocess has been run the first time, can also just use `yarn tsc`/`yarn watch-tsc` in packages/relay for faster compilation)

See dockers/config-sample/rly-gsn-relay-config-sample.json for a sample config file. Make sure to double check `"workdir"` specified in the config file - that's where the worker/manager keys and database will be created/read from

## To build/run with docker:

```
$ cd dockers/
$ ./jsrelay/dbuild.sh  # calls preprocess and webpack
$ docker-compose up -d
```

Similar to gsn's original docker-compose setup, this expects a config file in `gsn/dockers/config/gsn-relay-config.json` and creates/reads from the workdir in `gsn/dockers/gsndata`

```
$ cp dockers/config-sample/rly-gsn-relay-config-sample.json dockers/config/gsn-relay-config.json
```


# GSN Relay Server Original README:

[GSN, the Ethereum Gas Station Network](https://opengsn.org/) abstracts away gas to minimize onboarding & UX friction for dapps. 

This module contains Relay Server source code. Note that it is recommended to use a [Docker container](https://hub.docker.com/repository/docker/opengsn/jsrelay) `opengsn/jsrelay` to run your own Relay Servers.

[Please see the tutorial here.](https://docs.opengsn.org/relay-server/tutorial.html)


You are probably looking for one of these:

`@opengsn/provider` - a Web3 provider for client-facing JavaScript dapps that uses GSN to relay transactions.

`@opengsn/contracts` - all GSN contracts in Solidity language as well as their TypeScript type declarations.

`@opengsn/cli` - command-line tools made to help developers integrate GSN, test their integrations locally, or bring up relay servers on public Ethereum networks.

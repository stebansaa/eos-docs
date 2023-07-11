## Introduction

The Graph supports many networks such as Ethereum, EOSEVM, etc. This article will explain how to deploy TheGraph and build a test subgraph for EOSEVM.

## Setup Local Node

- Use Docker to run a local graph node and connect it to a blockchain via RPC.
- Clone the Graph Node repository: `git clone https://github.com/graphprotocol/graph-node/`
- Open `graph-node/docker/docker-compose.yml` and replace `http://host.docker.internal:8545` with `https://api.evm.eosnetwork.com/`.
- Navigate to `graph-node/docker` and run `./setup.sh` followed by `docker-compose up`.

## Deploy Contract to Index

- Deploy an ERC-1155 contract using OpenZeppelin's implementation.
- Deploy and note the contract address and block number.

## Setup Subgraph using OpenZeppelin

- Create a directory for the custom subgraph: `mkdir custom-subgraph`.
- Install OpenZeppelin subgraph package: `npm i @openzeppelin/subgraphs`.
- Create the configuration file: `mkdir custom-subgraph/configs` and create a file named `config.json` inside it.
- Add the following configuration details to `config.json`:
```json
{
  "output": "generated/sample.",
  "chain": "mainnet",
  "datasources": [
    {
      "address": "0xf248a9c50d0db54ea53b6ce0ca0e8d5861b908ed",
      "startBlock": 1218128,
      "module": ["erc1155", "ownable", "accesscontrol"]
    }
  ]
}
```

## Compile
Run the command npx graph-compiler --config custom-subgraph/configs/config.json --include node_modules/@openzeppelin/subgraphs/src/datasources --export-schema --export-subgraph.
### Create Subgraph
Run the command graph create generated/sample --node http://127.0.0.1:8020.
### Deploy Subgraph
Run the command graph deploy --ipfs http://localhost:5001 --node http://localhost:8020 generated/sample ./generated/sample.subgraph.yaml.
Once complete, visit http://localhost:8000/subgraphs/name/generated/sample to access and interact with the deployed subgraph.

## Test a query
Use the Graph Explorer or a GraphQL client to send queries and test the functionality of the subgraph.
Congratulations! You have successfully deployed TheGraph and built a test subgraph for EOSEVM.

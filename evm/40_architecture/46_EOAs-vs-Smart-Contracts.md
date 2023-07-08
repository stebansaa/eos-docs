---
title: EOAs vs Smart Contracts
contributors:
  - { name: Esteban Saá, github: stebansaa }
---
  
### What are EOAs?
EOA stands for Externally Owned Account. In the context of EOS EVM, an EOA is an account that represents an individual user or entity on the EOS EVM network. It is similar to the concept of an Ethereum account. EOAs have their own addresses, private keys, and balances.

##### What can you do with an EOA?
With an EOA, you can perform various actions on the EOS EVM network, including:

- Sending and receiving EOS EVM tokens or assets.
- Interacting with smart contracts by calling their functions.
- Participating in transactions and signing them with your private key.
- Managing your own account balance and transactions.

#### What you cant do with an EOA?
There are certain limitations to what you can do with an EOA:

- An EOA cannot directly execute code or perform complex computations.
- EOAs cannot store data or maintain state on the blockchain.
- They cannot create new smart contracts on their own.

#### Wallets
To interact with an EOA, users typically utilize wallets. Wallets provide a user-friendly interface for managing private keys, sending transactions, and interacting with the EOS EVM network. Wallets can be desktop applications, mobile apps, or web-based interfaces.

### What are Smart Contracts?
Smart contracts are self-executing contracts with predefined rules and conditions. They are autonomous pieces of code that reside on the blockchain and execute when triggered by specific transactions or events. Smart contracts on EOS EVM are typically written in Solidity or Vyper programming languages.

#### What can you do with a Smart Contract?
Smart contracts enable various functionalities and applications, including:

- Creating decentralized applications (dApps) that run on the blockchain.
- Implementing complex business logic and automating processes.
- Defining and enforcing rules for digital assets, such as tokens or non-fungible assets.
- Enabling secure and transparent transactions without intermediaries.
- Interacting with other smart contracts and external systems.

#### What you cant do with a Smart Contract?
Although powerful, there are limitations to what smart contracts can do:

- Smart contracts cannot access external data sources directly; they rely on oracles to fetch external information.
- They cannot perform actions that require off-chain interactions, such as interacting with the internet or making API calls.
- Smart contracts cannot initiate transactions on their own; they need to be triggered by external accounts (EOAs).

### How are EOAs and Smart contracts different?
EOAs and smart contracts are distinct entities on the EOS EVM network:

- EOAs represent individual user accounts and hold balances, while smart contracts are pieces of code that can also hold balances, yet they reside on the blockchain and execute predefined logic.
- EOAs can sign transactions and interact with smart contracts, but they cannot execute complex computations or store data on the blockchain directly.
- Smart contracts enable developers to define custom rules, automate processes, and interact with other contracts, but they cannot directly hold balances or initiate transactions.
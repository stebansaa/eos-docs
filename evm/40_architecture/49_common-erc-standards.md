---
title: EOAs vs Smart Contracts
contributors:
  - { name: Esteban Saá, github: stebansaa }
---

In the EOSEVM ecosystem, several widely adopted ERC (Ethereum Request for Comments) standards exist. These standards provide guidelines and specifications for implementing various functionalities and use cases on the EOSEVM network. Here are four commonly used ERC standards: ERC-20, ERC-721, ERC-777, and ERC-1155.

### ERC-20
ERC-20 is a standard interface for fungible tokens on the EOSEVM network. Fungible tokens are interchangeable and have identical values. ERC-20 tokens have methods to transfer tokens, check balances, and approve token spending on behalf of an address.

#### Example ERC-20 Contract
Here's an example of a basic ERC-20 token contract written in Solidity:

```
// contracts/GLDToken.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract GLDToken is ERC20 {
    constructor(uint256 initialSupply) ERC20("Gold", "GLD") {
        _mint(msg.sender, initialSupply);
    }
}
```


### ERC-721
ERC-721 is a standard for non-fungible tokens (NFTs) on the EOSEVM network. NFTs are unique and indivisible tokens that represent ownership of a specific item or asset. Each NFT has a distinct identifier, and they can be used for digital collectibles, unique assets, and more.

#### Example ERC-721 Contract
Here's an example of a basic ERC-721 token contract using the OpenZeppelin library in Solidity:

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/utils/Counters.sol";

contract MyNFT is ERC721 {
    using Counters for Counters.Counter;
    Counters.Counter private _tokenIds;

    constructor() ERC721("MyNFT", "NFT") {}

    function mintNFT(address recipient, string memory tokenURI) external returns (uint256) {
        _tokenIds.increment();
        uint256 newItemId = _tokenIds.current();
        _safeMint(recipient, newItemId);
        _setTokenURI(newItemId, tokenURI);
        return newItemId;
    }
}
```

### ERC-777
ERC-777 is an improved fungible token standard that incorporates additional features compared to ERC-20. It introduces advanced functionalities like hooks, which allow contracts to react to token transfers, and operator approvals, which enable third-party operators to handle tokens on behalf of token holders.

### ERC-1155
ERC-1155 is a multi-token standard that enables the creation of both fungible and non-fungible tokens within a single contract. This standard is particularly useful for projects that require the management of multiple types of tokens, such as gaming platforms or decentralized exchanges.

## Final thoughts
These ERC standards provide a foundation for building various token-based applications and use cases on the EOSEVM network. It's important to note that while these standards originated on Ethereum, they can also be implemented and utilized within the EOSEVM ecosystem.
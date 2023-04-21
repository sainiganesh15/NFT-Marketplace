# NFT Marketplace Project
This is a Solidity smart contract project for an NFT (non-fungible token) marketplace, where users can buy and sell NFTs using Ethereum.

The project consists of two contracts:

1. NFT.sol: This is an ERC721 contract that represents an NFT. It provides the ability to mint new NFTs with unique metadata.
2. Marketplace.sol: This is a marketplace contract that allows users to offer their NFTs for sale and other users to buy them. The contract charges a fee on each sale.

## Prerequisites

Before you can run the tests, make sure you have the following installed:

- Node.js
- Hardhat

## Installation

1. For Hardhat Installation
``` 
npm init --yes
npm install --save-dev hardhat
```

2. For running hardhat sample project install these dependencies:
```
npm install --save-dev @nomiclabs/hardhat-ethers@^2.0.5 @nomiclabs/hardhat-waffle@^2.0.3 
npm install --save-dev chai@^4.3.6 ethereum-waffle@^3.4.4 ethers@^5.6.2 hardhat@^2.9.2
```

## Using the Marketplace
To use the marketplace, follow these steps:

1. Connect your Ethereum wallet to the marketplace.
2. Browse the NFTs that are available for sale.
3. Click "Buy" on an NFT that you want to purchase.
4. Confirm the transaction in your Ethereum wallet.
5. Wait for the transaction to be confirmed.
6. The NFT will now be transferred to your Ethereum wallet.

## Connect development blockchain accounts to Metamask
- Copy private key of the addresses and import to Metamask
- Connect your metamask to hardhat blockchain, network 127.0.0.1:8545.
- If you have not added hardhat to the list of networks on your metamask, open up a browser, click the fox icon, then click the top center dropdown button that lists all the available networks then click add networks. A form should pop up. For the "Network Name" field enter "Hardhat". For the "New RPC URL" field enter "http://127.0.0.1:8545". For the chain ID enter "31337". Then click save. 

## Deploying Smart Contract to Localhost

1. Write your smart contract in Solidity and save it in the `contracts/` folder.

2. In the `hardhat.config.js` file, configure your local development network by adding the following:

```
require("@nomiclabs/hardhat-waffle");

module.exports = {
  solidity: "0.8.4",
  paths: {
    artifacts: "./src/backend/artifacts",
    sources: "./src/backend/contracts",
    cache: "./src/backend/cache",
    tests: "./src/backend/test"
  },
};

  ```

  3. In the `scripts/` folder, create a new script to deploy your contract to the local network:

4. Compile and deploy the smart contract using Hardhat

```
npx hardhat compile
npx hardhat run scripts/deploy.js --network localhost

``` 

This will deploy your smart contract to the local development network.
## Running the Tests

To run the tests, use the following command:

`npx hardhat test
`

This will run all the tests in the `test` folder.

## Tests
The tests are located in the `test` folder and cover the following scenarios:

Deployment
-  Should track name and symbol of the nft collection      
-  Should track feeAccount and feePercent of the marketplace       
Minting NFTs  
-  Should track each minted NFT 
Making marketplace items        
- Should track newly created item, transfer NFT from seller to marketplace and emit Offered event 
- Should fail if price is set to zero
- Should not fail if price is not greater than zero         
Purchasing marketplace items    
- Should update item as sold, pay seller, transfer NFT to buyer, charge fees and emit a Bought event 
- Should fail for invalid item ids, sold items and when not enough ether is paid 




Writing unit tests for smart contracts is an essential part of the development process. Hardhat makes it easy to write and run tests, and can be used with a variety of testing frameworks.

In this repository, we have demonstrated how to write unit tests for a sample smart contract called **NFT-Marketplace**.

## Contributing
If you would like to contribute to this project, please open a pull request.

## License
This project is licensed under the MIT license.
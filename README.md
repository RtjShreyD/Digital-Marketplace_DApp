# NFT MARKETPLACE, Decentralised Application (DApp)  

## Tech Stack 
### - NextJs, Hardhat, Solidity

## To Run :

1. Clone the repo
2. `npm i`
3. `npx hardhat node`
4. Let the hardhat node running, open new terminal,
    `npx hardhat run scripts/deploy.js --network localhost`
5. If the contract deployed successfully, it will return the contract address and transaction info in response.
6. `npm run dev`

Visit [localhost:300](http://localhost:300)

#### Notes : 
1. If the hardhat n/k node is restarted, the addresses and keys are same but the blockchain looses the previous running state, it's a new fresh chain each time.
2. In such case when the node was restarted, the project would not run properly and will probably show error message like 
    `Error: call revert exception (method="fetchMarketItems()", errorArgs=null, errorName=null, errorSignature=null, reason=null, code=CALL_EXCEPTION, version=abi/5.4.0)`
3. To resolve the error above, stop the DApp instance, re-deploy the contract and re-run the DApp instance. It will all start fresh.
4. Now, after starting fresh each time, make sure to re-connect Metamask to localhost:8545 (just click the localhost:8545 from networks drop down, it will sync).
5. If the 4th step was missed then we could become prey of errors in transaction failure, because the last block number which Metamask remembers is different and because its a fresh chain, the block number was initialised from 0, and only the contract was deployed so depending upon the number of interlinked contracts deployed the block number would be incremented and so will the prev hash be remembered.
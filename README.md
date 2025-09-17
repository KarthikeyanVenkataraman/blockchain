**Overview**

The PersonalLocker contract allows the deployer (owner) to store a secret message along with a password. The owner can update the message only by providing the correct password. The contract emits an event whenever the message is updated and provides a public view function to read the message

**Snapshot**

<img width="627" height="328" alt="image" src="https://github.com/user-attachments/assets/a5660610-5e53-413b-9ff3-a93d09c83abe" />


**Pre-requisites**
1.	Need Node.js in your local machine, In case, its not available Download node.js msi installer from https://nodejs.org/en/download/ ( For Windows )

**Development steps**
1.	Created a folder called "C:\blockchainpersonallocker"
2.	Used PowerShell to install install hardhat npm install --save-dev hardhat @nomicfoundation/hardhat-toolbox dotenv
3.	Create a javascript projects so that it creates the necessary folders required for the project like contracts, scripts etc.,

**Key files**
1.	contracts/PersonalLocker.sol - Contract files
2.	scripts/deploy.js - Deployment Script
3.	scripts/update.js - Update Script per requirement
4.	scripts/read.js - Reading the message (segregation of functions )
5.	hardhat.config - Config file
6.	.env file - This is not added in the repository as it contains sensitive information ( SECRET_PASSWORD, SEPOLIA_RPC_URL, PRIVATE_KEY)
7.	deployedAddress.json - Created when deploy.js is run. The address where the message is stored is written in this file so as to avoid hardcoding in update.js. update.js reads this file to update the message.

**Commands to run in local machine**
1.	Start local blockchain npx hardhat node. Sometimes Powershell can block running the script. So run Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass before running the previous script.
2.	Deploy contract locally npx hardhat run scripts/deploy.js --network localhost
3.	Update the contract with the message "Assignment Completed" npx hardhat run scripts/update.js --network localhost

**How did I deploy in Sepolia ?** 
For running the contract in Sepolia Testnet there are three things required
1.	API endpoint which points to Sepolia - Got it from Alchemy
2.	For getting ETH, used https://cloud.google.com/application/web3/faucet/ethereum/sepolia and provided the ETH Wallet address which is got from Metamask
3.	The Metamask pprivate key is stored in .env

Commands to run in Sepolia Its the same set of commands which is run in local expect that the --network localhost is replaced with sepolia --network sepolia

1.	npx hardhat run scripts/deploy.js --network sepolia
2.	npx hardhat run scripts/update.js --network sepolia

**Screenshot 1 - deploy.js execution – LOCAL**
 
<img width="940" height="463" alt="image" src="https://github.com/user-attachments/assets/d68b6f90-8d32-421d-9b32-12771fa4ed05" />

**Screenshot 2 - update.js execution - LOCAL**

<img width="940" height="378" alt="image" src="https://github.com/user-attachments/assets/66552c98-51ec-4d61-8bd4-5a0e402f25f2" />

**Screenshot 3 - Metamask Chrome Extension for Wallet**

<img width="467" height="698" alt="image" src="https://github.com/user-attachments/assets/3d7c28a1-898d-4604-ac4f-400426d818fa" />

**Screenshot 4 - Ethereum Sepolia Faucet**

<img width="940" height="525" alt="image" src="https://github.com/user-attachments/assets/7694d412-bef6-43b1-a9ff-2a0fe89a469d" />

**Screenshot 5 - Alchemy Dashboard showing App deployment**

<img width="940" height="519" alt="image" src="https://github.com/user-attachments/assets/3bef1435-9678-4aa1-a56b-2a677672c420" />

**Screenshot 6 - Deployment and Update in Sepolia**

<img width="940" height="381" alt="image" src="https://github.com/user-attachments/assets/0e14507c-0356-4703-b751-45b363679cf1" />


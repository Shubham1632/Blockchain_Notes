Basics:
---
- History:
	- satoshi nakamoto firsrt published the bitcoin
	- peer to peer transaction system in a decentralized network
	- powered by cryptograpy
	- 2016 vitalic buterin launched ethereum
	- 1994 -- nick szabo came up with idea of smart contract
	- Oracle Network-
			- blockchain cant interact with the outer world by itself ---> ( oracle problem )
			- thus some oracle networks does the work
			- chainlink is a decentralized oracle network
			- these are called hybrid smart contracts
	- web3 -
			- permissoinless web
			- decentralize ownership
			- Democratic Web 
- Smart contracts-
	- set of instructions executed in decntralized way without the need of centralized or third party entity
	- deployed on blockchain
	- solves the problem of trust as the terms of smart contract cant be violet
	- world from brand based to the math bases ( in terms of trust )
	- trust minimize agreements
	- read operation dosen't cost gas , only write operation does
	- are like public apis ---> anyone can access the function and information if they have address and abi
		- to secure this you need to have a whiltelist accounts specified in smart contract
		- only throes addresses can access the smart contract
	- when your smart contract is compiled into bytecode, before deploying it again got converted into OPSCODES. 
		- these are simple computation code that can run directly on the EV<. 
			- these are basic operation like ADD, SUB, DIV, SHA3 .... etc.
		- each OPCODE has specific gas asscociated with it
		- threfore complex transaction need more gas
		- but OPSCODE also generate fixed amount of gas reqired for smart contract
- Defi -
	- decentralized fianance
	- already around $200 billion + invested in defi protocols
	- provides more fair, more trance parent, more accountable financial system

- features-
	- decentralize
	- transparency and flexibility
	- security and immutability
- applications-
	- Defi
	- DAOs
		- groups that are govern completely decentralize
		- have rules which are implemented on smart contract on the blockchain
	- NFTs

- Transactions-
	- we sign the transactions with our private key
	- and people can verify it via our public key
		- they use digital signature algorithms (elliptic curve algorithm) to convert private key into public key
	- GAS- ( watch eip 1559 video from finematics)
		- to do  any kind of transactions your have to pay the gas money to miners ( pow )
			- depending on how busy the blockchain is the gas money increases
		- 1 ether = 1^9 gwei = 1^18 wei
		- each time we use trancsactons we end up burning some ethereum
- Gas-
	- transaction fees we need to pay in ethereum
	- the gas unit is a measure of amount of computational effort to execute a transaction on ethereum
	- gas is also necessary to prevent spamming 
	- 1 eth = 10^9 gwei = 10^18 wei
	- the cheapest transaction is to transfer eth from one account to another
		- this transaction cost 21000 gas unit
		- let take in consider following scenarios
	- the gas price set upon the user reqirement 
		- if he sets gas price high ---> his transaction will be mined faster
		- also a user can specify the gas limit (upper bound)
			- if your transaction spend less gas than limit then the remaining gas is refunded to your account
			- but the user must have that much of upper bound in the wallet
			- if transaction require more gas than limit, the transaction will fail
	- ethereum also put a block gas limit, to maintain the sync of rest of the network
	-  London Upgrade of 5th August 2021 ( EIP 1559 )-
		- Pre-London Upgrade-
			- before london upgrade the forumla was ( gas fees = gas spend * gas price )
			- let say gas price is 200 gwei, therefore for one transaction ( gas fees = 21000 * 200 gwei )
		- Post-London Upgrade-
			- benifits-
				- better gas fee estimatino
				- quicker transaction
				- burning eth used as transaction fees
			- Fees -
				- divided into three part 
					- base fee ---> minimun fee reqired to get into block (burned)
					- incentive --> directly paid to miner (set to 2gwei default))
					- max fee ---> the remaining fee will be returned 
			- the burned eth will maintain the equillibrium as there is not a limited supply of eth
			- variable block size-
				- before london upgrade the block computation size was fixed ---> 15M
					- which was not convinient in period of high demand 
				- now the block size is variable, a block will have a target size of 15M but can be extend up to 30M as per the demand 
				- now gas fees are dependent on previous block---> 
					- if previous block goes over 15M ---> gas fees increased 
					- if is less than 15M ---> gas fees decreased 
					- it maintained the equilibrium for block size
-  EVM- 
	- intro-
		- stands for ethereum virtual machine
		- manages the state of the ethereum
		- acts as a coin operated turnstile ---> (gate at wework hadpasar)
		- functionally it is a stack machine of 1024 items on it, and each item is 256 bit word
	- State transition-
		- ethereum , more than a distributed ledger acts as a distributed state machine
		- it transist from one state to another
		- Y(S, T) = S'
			- see it as a state transition function Y, a previous valid state S, set of valid transaction T and the new generated valid state.
			- state is stored at a large data structure called as Merkle Patricia tree
			- evm code (byte code)---> evm ---> ethereum node ---> hardware
	- OPSCODES-
		- 
- Provider and Signer-
	- Provider-
		- a provider is a ethreum node that allows you to read the data form its state. 
		- whenever you are reading something from the blockchain, you dont need to pay anything as the miners have done their work already.
	- Signer-
		- ethereum node that allows you to write data from the blockchain.
		- signer needs your private key to make transaction on behalf of your account
		- you can use the signer to do both the reading and writing the data
- ABI-
	- a human-readable format of your smart contract that is used to call correct byte-code from your smart contract
	- it contains rules and metadata about the contract, which help for the back and forth conversation with the smart contract.
- Mining-
	- how ethereum transctions are mined (proof of work)-
		- first there will be a mempoop of transactions that nodes have heard, but yet not included in block.
		- then the miner will group them to one block in a way that he will get maximum transaction fee to earn at the same time staying under block gas limit
			- miner will validate each transaction in the group (like signature, not froud etc. )
			- miner execute the transaction on their local copy. it rewards the transaction fees to their account
			- then the miner begins the process of creating a proof of work certificate for the block after verifying and executing each transaction
		- after cheking the legitimacy of the block, miner boradcast the block to the works with a certificate and new state of chain.
		- other miners then verify the certificate (which is easy to do) and execute all the trancaction in their local evm, and check if the state matches or not.
		- after doing all the verfication the block is added to chainn and state is upddated
		- all the transaction get removed form the mempool after block gets added.  
- Consensus-
	- mechanism to agree on the state of blockchain
	- eth and bitcoin follows nakamoto concenses
	- chain selection & sybil resistance ( not allow a user to create many nodes )
		- chain selection - whichever the blockchain have more number of block confirmation will proceed as main chain (longest chain rule)
		- 51% attack  -- > when someone have longest chain and 51% of nodes
		- sybil attack ---> when one person pretend to be many to take over the majority in network
	- Proof of Work-
		- features-
			- to reach to an agreement to the state of the blockchain, there should be a protocol which handles it
		- working-
			- miners compete with each other to mine the block 
			- they do complex mathematical operation which is hard to solve but easy to verify.
			- upon creating a block, miner share it with rest of the network and will get a freshly minted eth for the work
			- process-
				1. firstly miner selects a group of transactions to be added on the block
	1. then he put the data into a hashing function to get a target value
		1. less the target value is, more will be complexity of operation wiil be and vice versa
			1. to create a block a miner goes through a brut force method of putting values in the Hashfunction which accepts parameters like data, target and nonce to get a number
			2. to susessully complete the block the number generated through hashfunction should be less than the target
			3. 
		- chain selection-
			- if two miners produce a block at the same time then, it could cause the fork
			- to avoid that the "longest chain selecion rule" is used 
			- which accepts the chain with the more number of blocks 
			- this is also called as "Nakamoto Consensus", named after the inventor of bitcoin ---> Satoshi Nakamoto
			- because of the chain selection, the deleted blocks of the fork dosent get added to chain. they are called "Uncle Nodes"
			- but the Uncle Node Miners are  still rewarded by 1.75 eth for their hard work.
		- Finality-
			- after one minute of 6 blocks you can call the block as final, so there would be no further complications to the network
			- so there will be 99.99% chance that it will not reverted now
			- 
	- Proof of Stack -
		- features-
			- miners are called validator here
			- money/ eth on stack of each validator
			- misbehave will lead to loose the stack
			- less energy and less chances of cybil attack
			- cons - less decentralize ( may be )
		- Process-
			- now to become validator you need to invest 32 ETH 
			- validators will occasionally create a new block
			- most of the time they will validate the block validated by other validators
			- validators will receive a new block from peers and will re-execute the transaction, to confirm the block is valid
			- then he will upbote in favor of the block 
			- if enough votes are in favor of the block, the block is added to the chain
			- every 12 second (time of new block on ethereum) a new validator is selected to be a block processor.
			- validators need to have sufficient hardware, internet connectivity and other resources
			- if anyone fails to attend when chosen to generate block, they loose the insentive
			- if any validator misbehaves , his stake will be destroyed ( amount of stake slashed is depend upon what kind of misbehave done by validator)
		- facts-
			- from 22nd sept 2022 ethereum became pos from pow
		- Chain selection-
			- if fork (two different blocks validated concurrently) happens, the block with more votes is considered 
			- but sometimes an older block also could get  replaced due to the fork 
				- threrefore finality is used 
			- finality-
				- after every 32 blocks , an checkpoint is considered ( called epoches )
				- by the enough amount of votes, nth block is marked as justified and (n-32) block is marked as finalized 
				- the finalized block then would not be replaced or altered due to the fork
				- if after 4 epoches, the block is still remained to be finalized the network will slash the stakes of people who are giving the vote against, resulting in majority again gaining the  power
		- proof of stake is still new and have a big complex code, which can be sensetive to the attacks. so the community is trying to actively research and work on making pos consesus more secure and reliable.

- scalability-
	- more people will use blockchain and as each bock have limited space and speed of adding blocks is slow, the gas prices wiil skyrocket
	- thus we need some mechanism to handle the scalability
	- sharding-
		- layer 1 and layer 2

- IPFS-
	- InterPlanetory File System
	- it is a distributed and decentralized network to store the files
	- when we upload a file to the ipfs, it will divide the file into smaller chunk and distribute among the nodes
		- each file will have its own cid (content id)
		- to retrive the file, a node will search for other node who have these files and will also store the portion of it for future use
		- this way the file remain immutable
	- to update the file you  have to create a new CID and put the update file there, the old file will remain in the system as it is
	- Pinata is a third party software that makes ipfs faster
	- ENS-
		- Ethereum Naming System ( lookup system )
		- equivalent of DNS in the web3 world
		- to make your application fully decentralized you have to store the data of your application in the IPFS 
		- to retirve that data ENS is used ( it maps the data on IPFS )
		- refer the documentation
- Javasctipt-
	- Big Number-
		- big numbers in solidity are like uint256, which is eqivalent to ( 2^256-1), which is very big when we compare it with num in jacascript.
		- for eg. range of uint256 will be far more than num
		- therefore the libraries like ether.js and web3.js has custom functions called BigNumber, with wich we can handle data with large range
		- but to operate them we have to use funcions like .add( ) and .mul( ) instead of + and *
		- 
- EIP and ERC-
	- EIP stands for Ethereum Improvement Proposal
	- ERC stands for Ethereum Request for Comments
- ERC 20 -
	- token standard for creating tokens on the ethereum.  ( community/industry standard ) 
	- provides ans interface to your token contract.
	- it can be work as anything. ( mainly as an asset )
		- e.g. a casino token, currency, rewards etc.  ( mainly for financial applications ) 
	- we needed a standard to maintain the simplicity and usability.
	- It generalize the token so that it will be easy to other to handle token.
	- an eip then got converted into a ERC
		- ERC is not any kind of improvement in  the ethereum code 
		- but it is a improvement in the whole ethereum community.
	- a full erc20 compatible token should have 6 function and 2 events (predefined) in its token contract
	- Functions-
		- totalSupply ( ) --> return total number of supply of token
		- balanceof (address )  ----> returns balance of account owner
		- transfer ( address_to, value ) ---> transfer the specified amount to the specified address by msg.sender  ---> for each transfer function there is a event that emits called transfer ( will log the transactions in the ethereum logs )
		- transferFrom ( address_from, address_to, value ) ----> similar like transfer, but mainly used when a third party application wants to send the money on behalf of the sender.
		- approve ( address_spender , value ) -----> allows the spender to withdraw up to the specified amount of tokens from your account. also fires the approval event after successful call. 
		- allowance ( address owner, address spender ) ----->  it returns the amount of the token that spender still can use from the account
			- i.e. it will allow to use only 20% in the next 6 months
			- it is done to prevent the burning of token rapidly 
-  Token Vs coins-
	- token works as an asset or usis ed for a specific use
	- token can be utilized 
		- its not like currency that once it mint, it will be immutable and will have ownership of one person
		- it can be used and burnt
- Layer 2 ( Sharding )-
	- build on the main chain or layer 1 chain
	- to provide speed and scalability 
	- as majority of operations are carried out independent of layer 1 so its often called as off-chain solution
	- depend on layer 1 for  the consenses and security 


















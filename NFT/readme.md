NFT 
---
- Intro-
	- Stands for Non-Fungible Token
		- fungibility refer to the equivalence of the goods or any kind of assets.
	- token is a representation of something on the blockchain
	- it is a token which have unique characteristic for every token, and not fungible like ether
	- with ERC721 token standard, on which you can mint nft on any ethereum compatible chain.
		- a new protocol called ERC1155 is also there to mint nft
	- initially ethereum asked to upload the art and the nfts on the chain
		- but after some time they realize that the nfts are so much of expensive to store on the chain
		- so other solutions come over like to store the NFTs in a decentralized server and add it to the token URI
		- but the centralized server does not follow the content addressing
		- therefore the IPFS come into place which allowed users to upload a file and generate the content identification for the file
		- thats how the metadata from IPFS can be used to fetch into ERC721 protocol to mint an NFT
- Metadata-
	- we need to specify the stats and characteristics of NFT
	- in metadata we need to specify tokenURI

- Openzeppelin -
	- is as standard library for the smart contract development
	- it has all kind of contracts of various use-cases like erc20 token, erc721 token
	- we can just call the contracts and inherit the function from the openzepplin contracts to use them

- ERC-721-
	- info-
		- stand for ethereum request for comment - 721
		- a standard for non-fungible token (NFT)
			- standard is required to have a good system with which all other smart contract can interact with your contract
		- mostly used for collectibles
	- Interface-
		- an ERC721 contract must implement the ERC721 and ERC165 interfaces
	- Functions-
		- transfer -> does the transfer of ownership from one account to another
		- 


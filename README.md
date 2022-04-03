Battle NFT Character Creation
The battle NFTs is built with verifiable RNG using the Chainlink VRF
The NFTs change based on real world data using decentralized oracle
Added the randomized NFTs to the OpenSea Marketplace.

Generate a character
truffle exec scripts/fund-contract.js --network rinkeby
truffle exec scripts/generate-character.js --network rinkeby
truffle exec scripts/get-character.js --network rinkeby

This will create a new character with random stats! Depending how often deploy, one can pick which character by changing the dnd.getCharacterOverView(1) command in get-character.js to swap the 0. And It will give the overview of Battle NFT.

Deploy to Opensea
Since we have Battle NFTs created, we add a tokenURI. TokenURIs are the standard for showing the data of NFTs to the world. This makes it easier to store things like images since we don't have to waste the gas of adding them on-chain.

The TokenURI represents a URL or other unique identifier, and it is an .json file with a few parameters.

{
    "name": "Chainlink Knight",
    "description": "Defender against Flash Loan attacks, protector of #Defi protocols. Helping keep the smart contract kingdom secure, reliable, and safe. ",
    "image": "https://ipfs.io/ipfs/QmZGQA92ri1jfzSu61JRaNQXYg1bLuM7p8YT83DzFA2KLH?filename=Chainlink_Knight.png",
    "attributes": [
        {
            "trait_type": "Strength",
            "value": 52
        },
        {
            "trait_type": "Dexterity",
            "value": 55
        },
        {
            "trait_type": "Constitution",
            "value": 18
        },
        {
            "trait_type": "Intelligence",
            "value": 95
        },
        {
            "trait_type": "Wisdom",
            "value": 81
        },
        {
            "trait_type": "Charisma",
            "value": 93
        },
        {
            "trait_type": "Experience",
            "value": 0
        }
    ]
}

Battle NFT stores these images and meta data in IPFS: 
IPFS
IPFS companion
Pinata

IPFS is a peer to peer network for storing files. It's free and open sourced, and we can use it to host our tokenURI. The IPFS companion let's us view IPFS data nativly in our browsers like Brave or Chrome. And Pinata allows us to keep our IPFS files up even when our node is down.


 IPFS node is up, we can start adding files to it. We first want to upload the image of our NFT. What does this D&D character look like? Add it to your IPFS node and then "Pin" it. Once pinned, you can get the CID of the pinned file, and make sure it stays pinned by pinning it on the Pinata account. This will just help keep the data up even when our IPFS node is down.

Since Image is pinned and it provides link like this 

https://ipfs.io/ipfs/QmTgqnhFBMkfT9s8PHKcdXBn1f5bG3Q5hmBaR4U6hoTvb1?filename=Chainlink_Elf.png
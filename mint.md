# Chia NFT Minting Shell Script

## INSTALL INSTRUCTIONS

Install on Linux using:

```shell
git clone https://github.com/zakhikhan/chia-nft-minting-helper.git
```

## UPDATE INSTRUCTIONS

Update using
```shell
cd chia-nft-minting-helper
git pull
```
## DEPENDENCIES

* Linux is the only OS that is supported at the moment. Not tested on MacOS, though I do have a Mac so I will test it soon.
* Chia wallet 1.4 or greater
* curl and jq packages (install instructions below)

## USAGE INSTRUCTIONS

#### 2. NFT MINTING
 1. Follow instructions at https://devs.chia.net/guides/nft-intro to create a DID wallet and NFT wallet in the CLI. Make sure the wallet is funded with enough XCH to mint an NFT. If you don't have enough, you can get some from the Chia faucet.

 2. Make sure Chia installed and running and synced Chia wallet.

 3. Create /images in chia-nft-mint-helper and add all image files to the /images directory, saved in the format of 'image[x].jpg' (or other extension), with x representing the number in minting order. Do the same for metadata files in the /metadata directory.
	example: files must be saved as image1.jpg, image2.jpg, image3.jpg, etc. 
		metadata must be saved as metadata1.json, metadata2.json, metadata3.json, with the numbers on the images and metadata matching up for the same NFT.
	Note: If you used the metadata generation script the metadata will already be in the proper location for you. Just make sure the numbers on the metadata filenames match up with the image filenames.

4. Sign up for an account at nft.storage and get an API Key

5. Customize all variables in the script 'mintingscript.sh' by opening it with a text editor. Make sure you are clear on what they are all for. Many questions can be answered in the Chia NFT documentation, linked above.

6. Install the dependencies: curl and jq. If using Ubuntu with apt, run the following commands:

```shell
sudo apt update
sudo apt upgrade
sudo apt install curl
sudo apt install jq
```
6. Run the script by navigating to the directory of the script and executing the command './mintingscript.sh'. (You may need to change permissions on `mintingscript.sh` to executable with `sudo chmod +x mintingscript.sh`)

9. Before minting each NFT, the script will prompt you to review the minting command. Please review this command against the Chia documentation for minting a single NFL. Once you continue, the NFT will be created , final & permanent.

10. Continue through the process to mint all NFTs. If you have to stop the script, or get an error, you can open the script in a text editor and change the 'i' variable to resume wherever you left off.

[IMPORTANT NOTE: Please wait at least 1 minute in between minting each NFT. In the near future, we will add a function to delay minting automatically, but in the meantime, if you mint too quickly, the mint will fail.]



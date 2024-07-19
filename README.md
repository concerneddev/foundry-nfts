# Verifed Contracts On Etherscan:

[Contracts](https://sepolia.etherscan.io/address/0x48250e68b496838ce0f9e73a2ba6e2b12224e34b#code)

# Setup:

## foundry.toml

```
ffi = true
fs_permissions = [{ access = "read", path = "./broadcast" }]
```

## OpenZeppelin

Run :
```
forge install @openzeppelin/openzeppelin-contracts --no-commit
```

*foundry.toml* :
```
remappings = ["@openzeppelin/contracts=lib/openzeppelin-contracts/contracts"]
```

## cyfrin/foundry-devops

Run :
```
forge install cyfrin/foundr-devops --no-commit
```

# Commands:

## Deploying 

After adding the relevant data in the *.env* file, run this:
Sourcing the *.env* file:
```
source .env
```

Deploying on Sepolia Testnet :
```
forge script script/DeployBasicNFT.s.sol --rpc-url $SEPOLIA_RPC_URL --private_key $PRIVATE_KEY --broadcast --etherscan_api_key $ETHERSCAN_API_KEY --verify
```
OR
```
make deploy ARGS="--network sepolia"
```

## Minting through console

Run :
```
forge script script/Interactions.s.sol:MintBasicNFT --rpc-url $SEPOLIA_RPC_URL --private_key $PRIVATE_KEY --broadcast --etherscan_api_key $ETHERSCAN_API_KEY --verify
```
OR
```
make mint ARGS="--network sepolia"
```


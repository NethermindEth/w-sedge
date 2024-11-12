# Sedge Workshop Resources

This repository contains all necessary resources for the Sedge workshop, including setup instructions, commands, and supporting materials for running Ethereum nodes and validators using Sedge.

## Install Sedge:

If you want to install sedge, all you need to do is access [our docs page](https://docs.sedge.nethermind.io) and you will be able to copy the command based on your system, for example for Linux:
```
bash <(curl -fsSL https://github.com/NethermindEth/sedge/raw/main/scripts/install.sh)
```

## Install dependencies
You can check if you have any missing dependencies with:
```
sedge deps check
```
and then if yes, you can install them with:
```
sedge deps install
```

## Running a Sedge Node on Holesky
To run a node you can either use:
```
sedge cli
```
and go through the process with the interactive mode or execute commands:
```
sedge generate full-node --latest -n holesky -c prysm -e nethermind
sedge run
```

## Running a Validator
(Optional) if you want to set up a new validator and do not have keys you can generate them like this:
```
sedge keys
```
and follow the instructions in guide.

After making sucesfull deposit you can import your keys to validator component using:
```
sedge import-key prysm
```

## Running Monitoring Stack
(Optional) You can set up monitoring stack to your node by using:
```
sedge monitoring init default
```

## Running Sedge on OP
To run OP-mainnet node use below command (replacing placeholder for L1 components urls):
```
sedge generate op-full-node -n mainnet --execution-api-url URL_TO_EL_L1_RPC --consensus-url URL_TO_CL_L1_API
```

Running it without `--execution-api-url` and `--consensus-url` will create also L1 node to connect to it.

## Running Sedge on Base
Similar to OP mainnet base can be generated in the same way using `--base` param:
```
sedge generate op-full-node -n mainnet --base --execution-api-url URL_TO_EL_L1_RPC --consensus-url URL_TO_CL_L1_API
```

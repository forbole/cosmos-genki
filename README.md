# Cosmos Testnet genki-1000
Gathering spirits from the Cosmos

![Spirit Bomb](spirit-bomb.gif)

Instructions for the Network Start

## Submit a genesis transction.

We are trying to start a testnet from the Cosmos Validator Community to test the bug fixes and practice the start of Game of Stakes.

To be bonded at genesis, you need to generate a genesis transaction and submit it by 2018-12-07 15:00 UTC.

The final genesis.json will all the bonded particpants will be released before the end of 2018-12-07 UTC. We are going to use the tool developed from Certus One to verify the gentx files and create the genesis file.

### To generate a genesis transaction,

install `v0.27.1` of the Cosmos SDK.

run `gaiad init`

Download [genesis](genesis.json) to `$HOME/.gaiad/config/genesis.json`

if you need to recover the key you used for signup do

`gaiacli keys add <key-id>  --recover`


```
gaiad gentx \
  --amount 10000STAKE \
  --commission-rate "0.10" \
  --commission-max-rate "1.00" \
  --commission-max-change-rate "0.01" \
  --pubkey $(gaiad tendermint show-validator)  \
  --name <key-id>
```

This will generate a file roughly like `$HOME/.gaiad/config/gentx/gentx-c00ce0b868bd5d5576d23f0ad1090f3f478b7961.json`

Please submit this file in `gentx` folder in a Pull Request on this repository.

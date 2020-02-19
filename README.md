# Setup Pre Requirements:

## Install eosio.cdt 1.7.0

### Ubuntu:

```
wget https://github.com/eosio/eosio.cdt/releases/download/v1.7.0/eosio.cdt_1.7.0-1-ubuntu-18.04_amd64.deb
sudo apt install ./eosio.cdt_1.7.0-1-ubuntu-18.04_amd64.deb
```

### Mac OS X:

```
brew tap eosio/eosio.cdt
brew install eosio.cdt
```

## Install Solidity 0.6.0

### Ubuntu 18.04:

```
sudo add-apt-repository ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install solc
```

### Mac OS X:

```
brew update
brew upgrade
brew tap ethereum/ethereum
brew install solidity
```

# Build

```
git clone --branch evm4eosio https://github.com/learnforpractice/eos-with-evm evm4eosio --recursive
cd evm4eosio
./script/eosio_build.sh
```

## Start a Local Testnet

```
./nodeos/nodeos --http-server-address 127.0.0.1:8888 --p2p-listen-endpoint 127.0.0.1:8801 --verbose-http-errors --http-max-response-time-ms 50 --data-dir dd --config-dir cd --wasm-runtime eos-vm-jit --contracts-console -p eosio -e --plugin eosio::producer_plugin --plugin eosio::chain_api_plugin --plugin eosio::contract_api_plugin 
```

# Try It
Please see readme in https://github.com/learnforpractice/evm4eosio-demo

# License

[GPL](./LICENSE)

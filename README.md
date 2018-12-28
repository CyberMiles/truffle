This repository is a fork from [trufflesuite/truffle](https://github.com/trufflesuite/truffle) with Lity support.

### Install

```
$ git clone https://github.com/CyberMiles/truffle.git -b lity
$ cd truffle
$ npm install -g lerna yarn
$ npm run bootstrap
$ export PATH="$PWD/node_modules/.bin:$PATH"
```

### Quick Usage

```
$ mkdir truffle_project
$ cd truffle_project
$ truffle init
$ truffle compile
```

### Example

Here we use [BTCRelay.sol](https://github.com/CyberMiles/smart_contracts/tree/master/BTCRelay) as an example.

```
$ curl -o contracts/BTCRelay.sol https://raw.githubusercontent.com/CyberMiles/smart_contracts/master/BTCRelay/BTCRelay.sol
$ truffle compile
```

If you want to deploy contracts to CyberMiles Travis network, you should edit `truffle-config.js` for network settings.

```
const web3 = require("web3-cmt");

...

networks: {
  testnet: {
    provider: () => new web3.providers.HttpProvider('<your_rpc_server_here>'),
    network_id: "*",
  },
}
```

and deploy it on testnet:

```
$ truffle deploy --network testnet
```

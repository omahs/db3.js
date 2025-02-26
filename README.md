# What is db3.js

[![npm](https://img.shields.io/npm/v/db3.js?style=flat-square)](https://www.npmjs.com/package/db3.js)
![npm](https://img.shields.io/npm/dw/db3.js?style=flat-square)

db3.js is the [db3 network](https://github.com/dbpunk-labs/db3) javascript API and you can use it to write and query JSON documents against the db3 network.
and you can build fully decentralized applications combining [web3.js](https://github.com/web3/web3.js) and db3.js


# How to use db3.js

The goal of db3.js is compatible with [the indexeddb api](https://www.w3.org/TR/IndexedDB/) and you can use db3.js like using indexeddb, even you can use all libraries based on indexeddb e.g. [rxdb](https://github.com/pubkey/rxdb)

```typescript
/*
|----------------------------|
| use db3js open a database  |
|----------------------------|
*/

// build sign function
const sign = await getSign()

// build database factory
const dbFactory = new DB3Factory({
    node: 'http://127.0.0.1:26659',
    sign,
    nonce
})

// open database with a address
const db = dbFactory.open("0x5ca8d43c15fb366d80e221d11a34894eb0975da6")
```

## Show Your Support
Please ⭐️ this repository if this project helped you!

# Build

## 0.Checkout

```shell
git clone https://github.com/dbpunk-labs/db3.js.git
git submodule update --recursive
```

## 1.Run DB3 Localnet

```shell
cd tools && bash start_localnet.sh
```

## 2.Run Testcase

```shell
git submodule update
# install the dependency
yarn
# generate the protobuf
make
# run test
yarn test
# format the code
yarn prettier --write src
# run benchmark
yarn benny-sdk
```

## 3.Run WPT Case

please setup the wpt enviroment with [these steps](https://web-platform-tests.org/running-tests/from-local-system.html#system-setup)
```shell
yarn build:wpt
cd thirdparty/wpt && ./wpt serve
```

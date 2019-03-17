# Parity Clique

This is an out of tree EIP225 (Clique Proof-of authority consensus engine) implementation for Parity. This implementation
is mostly authored by Yucong Sun, and there is some other changes pulled in from peoples noted in credits. It is also the software
version in use in my active Goerli authority node (Yucong Sun Authority as seen in https://exploer.goerli.net).

# What is working:

- [X] Sync & full block validation for clique based ethereum networks.
- [X] Seal blocks and process votes according to EIP225 rules.
- [X] built-in genesis JSON files for easily connecting to Rinkeby, Goerli, and Kotti network.

# TODO
- [ ] an tool to generate genesis json file for clique engine.
- [ ] JSON rpc for voting.

# How to build and run

Download patched source code zip file from https://github.com/thefallentree/parity-clique/releases , extract and ```cargo build --release --features=final``` 

# How to generate patched source code zip file.

```
$ git clone -b <release tag> https://github.com/thefallentree/parity-clique 
$ cd parity-clique
$ git submodule init && git submodule update
$ cd parity-ethereum
$ patch < ../patch-v2.4.0.patch -p 1
$ cargo build --release --features=final
```

# How to run an local clique based ethereum network

```
$ target/debug/parity --chain /tmp/1.json -l engine=trace,miner=trace --force-sealing --reseal-min-period=1000 --reseal-max-period=1000 --engine-signer=<YOUR ADDRESS> --password /tmp/1
```

# Seal on goerli
```
$ target/debug/parity --chain goerli -l engine=trace,miner=trace --force-sealing --reseal-min-period=1000 --reseal-max-period=1000 --engine-signer=<YOUR ADDRESS> --password /tmp/1
```

# What you can use it for
- [X] connect to rinkeby network by ```./parity --chain rinkeby```
- [X] connect to goerli and kotti network.
- [X] Run an local Clique based ethereum network with parity alone (tutorial pending)
- [X] Join an cross client Clique based ethereum network as an Full Node, together with Geth, Pantheon and other clients.

# Upstream

This patch will be updated in best effort to keep up with latest release from paritytech/partity-ethereum, but will not be upstreamed. (see https://github.com/goerli/parity-goerli/issues/44 for context).

If you want to make a feature request, please raise a issue.

# Credits

genesis JSON files for Goerli & Kotti are from @5chdn.

# parity-clique

This is an out of tree maintained EIP225 (Clique Proof-of authority concensus engine) implementation for Parity. The engine implementation
is mostly authorized by Yucong Sun, and there is some other changes pulled in from peoples noted in credits.

# What is included:

- [X] Sync & full block validation for clique based ethereum networks.
- [X] Seal blocks and process votes according to EIP225 rules.
- [X] built-in gensisis JSON files for easily connecting to Rinkeby, Goerli, and Kotti network.

# TODO
- [ ] JSON rpc for voting.

# How to build and run
```
$ git clone ....
$ cd parity-etherum
$ patch < ../patch-v2.4.0.patch -p 1
$ cargo build --release --features=final
$ target/release/parity <your options>
```

# How to run an local clique based ethereum network
pending tutorial

# What you can use it for
- [X] connect to rinkeby network by ```./parity --chain rinkeby```
- [X] connect to goerli and kottii network.
- [X] Run an local Clique based ethereum network with parity alone (tutorial pending)
- [X] Join an cross client Clique based ethereum network as an Full Node, together with Geth, Pantheon and other clients.

# Upstream

This patch will be updated in best effort to keep up with latest release from paritytech/partity-ethereum, but will not be upstreamed.
If you want to make a request, please raise a issue.

# Credits

genesis JSON files for Goerli & Kotti are from @5chdn.

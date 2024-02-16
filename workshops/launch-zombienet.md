# Launch an ephemeral Polkadot testnet with Zombienet

​Zombienet, a tool developed by Parity Technologies provides a rich set of capabilities for running integration tests on blockchains connected to Polkadot. It's designed as an integration testing tool for parachain development teams. But in this workshop, you'll use it's basic functionality to launch your own local parachain network and learn about how connecting chains to Polkadot works under the hood.

---

## Workshop plan

_ Learn about the big picture: relay chain binary and parachains, genesis config, executable
- Setup Zombienet locally
- Follow the steps to run the test net
- Launch networks with different configurations

---

## Let's learn about some background stuff first..

TODO

Polkadot is a network of "appchains" we call parachains.

Chains need to be prepared to be able to connect to the relay chain. A couple key points:
- Registering parachain ID
- Spec raw, genesis header, genesis state, genesis wasm

---

## Network nodes

- Relay chain nodes: the validators 💪
- Collator nodes: the parachain nodes ⚡️

---

## Clone and download the workshop repo

- Contains binaries for the relay chain node and the parachain node 
- Compiled `polkadot-v1.1.0` including all its system parachains

Fun fact: the entire repo took 61m 19s minutes using the Macbook pro M1 chip. 🤯
But that's a lot of parachain binaries ... _you don't want to do this!_

---

_Food for thought: in a way, parachains are just like mega complex smart contracts.._

---

## Node CLI

Fun little activity.. Run to interact with your node:

```bash
./bin/polkadot-parachain --help
```

---

## Install Zombienet

Although you can set up zombienet to on the system path of your machine, I recommend this:

```bash
wget https://github.com/paritytech/zombienet/releases/download/v1.3.68/zombienet-macos -P    
```

---

## Big picture

(while we wait for Zombienet to install.. )

- Take the relay chain binary (polkadot)
- Take our parachain binary
- Pass them into a config
- Run the network with tests

---

## Zombienet CLI

At this point we've successfully installed Zombienet.

Let's check out the CLI commands..

---

## Quest #1: simple parachain network

We'll do this together!

Launch a network with a single parachain.

Checklist:
- Make the binary executable
- Download the pre-compiled binaries from your arch (x64_86/aarch64) from https://github.com/Polkadot-Blockchain-Academy/pba-zombienet/releases, rename them and make executables
- See Windows [setup instructions](https://github.com/Polkadot-Blockchain-Academy/pba-zombienet?tab=readme-ov-file#windows)
- create a `Config.toml` file to specify how we want to configure the network
- run the `zombient spawn` command

```bash
zombienet-macos -p native spawn ./bin/config.toml
```

---

## Download your appchain binaries

For this workshop we'll use the provided binary from the repository provided. 😎

---

## Launch the network

```bash
./zombienet/zombienet-macos -p native -l silent spawn ./zombienet/Config.toml
```

---

Let's have a look what Zombienet does under the hood...

- `./bin/polkadot build-spec --chain rococo-local`
- `./bin/polkadot-parachain --name parachain-collator01 --node-key`
- Alice, Bob and Charlie are funded too

---

## Quest #2: add new system chains to the network and run tests

- Using the binaries in the folder, add new system chains
- Update the config file to include different tests

---

## Troubleshooting

- make sure the permissions for your binaries are updated `chmod +x`
- check your zombienet version is up to date (or recent enough!)

---
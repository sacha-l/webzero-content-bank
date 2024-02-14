# Polkadot for contract dApp builders

Presenter: Sacha Lansky

​There are many Polkadot layer-1 chains you could launch your dApp on including AlephZero, Astar, Moonbeam. Different chains also have different smart contract execution VMs — the popular ones being the famous EVM and WebAssembly-based "pallet contracts". In this workshop you'll get hands on experience learning ink!, the smart contract language that compiles to WebAssembly and learn about the options for deploying your dApps on Polkadot.

---

This workshop aims to give you a lay of the land of the different smart contract platforms on Polkadot and introduce you to ink! &mdash; the native smart contracting language for the Polkadot ecosystem. 

---

## Learning objectives

* Learn what options you have for **building and deploying** smart contracts on Polkadot 
* Learn how to get started with ink!
    * Set up your local environment
    * Deploy your first ink! smart contract
* Complete a mini-quest and earn some DOT
* Learn where to go next

---

Spoiler alert: There's no such thing as deploying smart contracts "to Polkadot" (at least not today).

You deploy to _Polkadot appchains (aka parachains) that support smart contracts_. 💡

---

## Background

- Polkadot is a network of specialized layer-1 chains (_a.k.a appchains, a.k.a parachains_) secured by the same validator set
- Certain appchains support EVM compatible contracts
- Certain appchains support WASM (WebAssembly) contracts
- Some appchains support both EVM and WASM contracts!

---

## Two type of smart contracts for Polkadot

- EVM compatible (most popular language is Solidity) 🙌
- WASM (`pallet-contracts`) compatible (most popular language is ink!) 🦀

---

## EVM compatible appchains

- Moonbeam
- Unique network
- Centrifuge
- Astar

---

## Wasm compatible appchains

- Astar 
- Phala
- Pendulum
- Amplitude 
- t3rn
- Zeitgeist 

And Aleph Zero of course.. ! 

See: https://use.ink/#where-can-i-deploy-ink-contracts

---

## Paying for gas 

Each appchain has their each have their own tokens to pay for transaction fees

---

Q: How can I tell if a chain is smart contract compatible? 

---

## ink! vs. Solidity

|                       | ink!                        | Solidity      |
| :-------------------- | :-------------------------- | :------------ |
| Virtual Machine       | Any Wasm VM                 | EVM           |
| Encoding              | Wasm                        | EVM Byte Code |
| Language              | Rust                        | Standalone    |
| Overflow Protection   | Enabled by default          | Yes           |
| Constructor Functions | Multiple                    | Single        |
| Tooling               | Anything that supports Rust | Custom        |
| Versioning            | Semantic                    | Semantic      |
| Has Metadata?         | Yes                         | Yes           |
| Multi-File Project    | Planned                     | Yes           |
| Storage Entries       | Variable                    | 256 bits      |
| Supported Types       | Docs                        | Docs          |
| Has Interfaces?       | Yes (Rust Traits)           | Yes           |

---

## Get your terminals out! 

What we need to do:

- environment setup
- cargo contract
- contracts UI

---

## Environment setup checklist

Steps: https://use.ink/getting-started/setup

---

## Basic ink contract

- cargo contract commands
- ink macros
- build contract
- artifacts

---

## Contract parts

- storage, structs, derive impls
- contructors, messages
- can have two constructors: default or some custom (decent runthrough here https://youtu.be/DV5n-GD9sOA?t=1988)

---

## Deploying to testnet

- ROC faucet
- Contracts UI

---

## Quests

Workshop quests are a way to keep you engaged and help you put what we've learnt today to practice!

**Today's quests:**

1. Setup your local environment and compile the flipper contract
2. Deploy the contract to Rococo using the contracts UI

**Reward eligibility**: Submit screenshot proofs as a PR to the `contracts/quests` folder in the workshop repository _within 1 hour after this workshop_ to be eligible for a small reward of 4 DOTs. 🚀

Completion of bonus quest receives 3 more DOTs!

---

## Quest #1: 

Deploy the contract to Rococo using the contracts UI!

1. Build contract
2. Get ROC
3. Deploy to Rococo
5. Interact with your contract

---

## Smart contract limitations

- Smart contracts written in ink! are a great starting point for developing applications in the Polkadot ecosystem.
- For many applications, smart contracts are good enough. However, they are exposed to the inherent limitations of the smart contract execution environment:
    - Sharing of blockspace with other smart contracts, volatile "gas" fees.
    - Default model enforces gas fees being paid by the end user.
    - Relative poor performance of interpreted smart contract (untrusted) code compared to pre-compiled Parachain runtime (trusted) code.
    - Limited access to the host chain environment and any special functionality provided by an extensive suite of customisable FRAME pallets.

https://use.ink/migrate-ink-contracts-to-polkadot-frame-parachain#example-migration


---

## Quest #2: turn an ink! contract into a parachain (bonus)

This workshop hasn't taught you about FRAME -- the framework for building Polkadot appchains. But.. a hugely under appreciated aspect of ink! is how easy it is to turn a prototype written in ink! into it's own appchain.

Time permitting... let's follow the steps [here](https://use.ink/migrate-ink-contracts-to-polkadot-frame-parachain#example-migration) and:

- Create a repo with a basic FRAME pallet structure
- Migrate the parts of your contract to a FRAME pallet

Make sure to join us later to dive deeper into building with the Polkadot SDK!

---

### Tools and libs

- Open Brush: https://use.ink/getting-started/use-openbrush
- Swanky Suite: https://use.ink/getting-started/swanky 
- ink! analyzer: https://use.ink/getting-started/ink-analyzer
- Polkadot Contract Wizard: https://contractwizard.xyz/
- ink!athon: https://use.ink/getting-started/inkathon
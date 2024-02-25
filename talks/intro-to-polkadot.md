# A brief intro to Polkadot’s design and capabilities 🦄

In this talk, we'll learn about how Polkadot works at a high level. We'll learn about the different terms you may come across such as "parachains", "xcm", "relay chain" and how these relate to terms used in Ethereum.

<<<<<<< Updated upstream
Note: arc starting by what is Polkadot, how its design meets the needs it addresses, beyond Polkadot 1.0.
=======
Note: arc starting by what is Polkadot, how its design meets the needs it addresses, beyond Polkadot 1.0. Style: visual focus.
>>>>>>> Stashed changes

---

## Talk outline

<<<<<<< Updated upstream
* Philosophy: a network designed to secure specialized blockchains and evolve over time (2 key features to cover)
    * Specialized chains and interoperability
    * Meta-protocol governance
* Terminology: Relay chain, Parachain, DOT token
* Polkadot's design
=======
* Philosophy: a network designed to secure specialized blockchains and evolve over time without the intervention of a single governing body (2 key features to cover)
    * Specialized chains and interoperability
    * Meta-protocol governance

* Polkadot as a protocol that's self-sustainable
    * Pays for actors that help it prosper (protocol upgrades, maintainence, features upgrades)
    * Upgradable
    * Examples: events paid by treasury, tips, marketing initiatives, 

* Visual: it's a network that provides blockspace
* Visual: designed to be self governed
* Terminology: Relay chain, Parachain, DOT token

* Why Polkadot's design?
>>>>>>> Stashed changes
    * Problems it has identified: Scalability with interoperability and security for a multichain future + futureproofness
    * How it addresses those problems
        * Scalability: specialized blockchains, built for a specific purpose and optimizing in what they do. Parachains inherit economic security of Polkadot itself
        * Interoperability: allow all parachains to communciate and be collaborative by default, access to the web3 ecosystem even outside the Polkadot network
    * Architectural overview
    * Nominated proof of stake
    * Consensus
<<<<<<< Updated upstream
* Building and deploying parachains
* What's Polkadot beyond the tech
* The road ahead Polkadot 1.0 
    * Blockspace as a service (compute machinery)
    * Beyond verifying blockchains
    * Coreplay: reframing how to make use of the resource Polkadot provides
=======

* Building and deploying parachains
* The Polkadot System (chains that have DOT as their native token)
* Highlight:
    Accessibility -> resiliance -> ??
* What's Polkadot beyond the tech
    * DOT token
    * OpenGov
    * Staking
* The road ahead (>Polkadot 1.0) 
    * Blockspace as a service (compute machinery)
    * Beyond verifying blockchains
    * Coreplay: reframing how to make use of the resource Polkadot provides
* Technical and financial support
* Q&A (time permitting)
>>>>>>> Stashed changes

---

## Polkadot's philosophy

* Future is multi-chain
* Chains need to be able to evolve

<<<<<<< Updated upstream
=======
Note: show what we learn from this visual. Show alpha.chainviz.app

>>>>>>> Stashed changes
---

## Terminology check

* Parachain
* Collators
* XCM

Note: show https://twitter.com/0xgoku_/status/1757479157661889023?t=Yb-S2fsBC8Vtd0t5dn3XTQ

---

Show alpha.chainviz.app

---

<<<<<<< Updated upstream
=======
Show xcm visualizer

---

>>>>>>> Stashed changes
## Problems / solutions

* Scaling is hard / specialized chains
* Securing multiple chains is hard / shared security model
* No good to have chains in isolated from eachother / interoperability protocol
* Coordinating upgrades is centralized / on-chain governance mechanism

---

## Architectural overview

* Relay chain
* Parachains
* Bridges

---

## Types of nodes

* Polkadot network validator nodes
* Parachain collator nodes

Note: collators are assigned a specific group of validators, to get their blocks validated 

---

##  Shared security
 
* Attacking one parachain means attacking the entire network

---

* Architecture simplified
    * relay chain provides validator set and shared security for appchains (parachains) connected to it
    * appchains run collator and relay chain nodes to sync to relay chain
    * relay chain provides compute
    * parachains pay for execution and verification of parachain blocks

---

* Why appchains?
    * shared security
    * interoperability with other appchains
    * have your own token for transaction fees
    * customize logic on the state machine level (e.g custom transaction fee logic, custom consensus mechanism)

---

## PolkadotSDK
### Substrate
#### FRAME

* Building appchains
    * use Substrate, part of the PolkadotSDK modular framework for building appchains
    * use FRAME, a library of reusable modules (e.g. tokens, governance)

---

## Beyond Polkadot

* Governance / OpenGov
* Staking
* Bonding

---

## What people are building on Polkadot

* Parachains
* Infrastructure
* Wallets

---

## The road ahead Polkadot 1.0 

* Blockspace as a service (compute machinery)
* Beyond verifying blockchains
* Coreplay: reframing how to make use of the resource Polkadot provides

---

## Technical and financial support

* Onchain treasury funding via OpenGov
* W3F Grants
* Substrate builders program
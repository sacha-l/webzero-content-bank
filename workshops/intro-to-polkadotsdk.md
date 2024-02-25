# Intro to Polkadot SDK

​Dive into the Polkadot SDK to learn the basics about building a Substrate based appchain.
You'll write simple FRAME pallets and learn about the different components of the Polkadot SDK by completing a fun quest as you progress through the workshop.  

Key topics: Polkadot SDK, FRAME pallets and Substrate node

---

Note: from previous we learnt about some tools and libraries, now we can put them to practice, focusing on building a component to customize an appchain.

---

## Workshop goals and objectives

* Learn the basics of FRAME
* Build a pallet
* Be able to integrate a pallet into a template node

---

## Agenda

- Set up your machines
- Explore the Polkadot SDK
- Build a basic "pallet"
- Quests

---

## Set up your machines 

Install Rust! 🦀

_Note: Setting up Rust could take up to 10 minutes depending on your machine, so head to the installation guide and do that! Let me know if you're stuck._

---

By the end of the workshop you'll know how to create a pallet, integrate it to a node template and interact with it locally.

_Show extended node template running and interact with basic pallet._ 

---

## How workshop quests work

- We learn something, some concept
- We put it to practice
- Prove that you've completed each quest and you're entitled to a small reward!

---

## Polkadot SDK
### Substrate
#### FRAME

---

_Let's jump right in._

---

## What is the SDK?

- Libraries to build standalone blockchains
- Libraries to make your blockchain polkadot compatible
- Libraries specific to the polkadot protocol

---

Diagram of a Substrate node to illustrate SDK capabilities.

---

## Follow along

Open the Polkadot SDK in your browser.

Note: go over releases, core libraries, FRAME pallets.

---

## Releases 

Throughout the workshop we'll use the `polkadot-v1.1.0`.

It's important to always make sure you're using the same releases throughout your projects: FRAME pallets, parachain templates etc. Otherwise you'll run into compatibility issues. 🥴

---

## Polkadot SDK libraries for building blockchains

Substrate
* Client facing code: networking, consensus
* Runtime module code 👈 _our focus today_

Cumulus
* Parachain compatibility code

---

## Types of modules (aka "pallets")

Pallets can literally be anything you can think of that gives you capability to alter the sate of your chain.

Notes: Consensus related, governance related, app-specific, asset related.

---

Q: What do you think are the most used pallets? By who?

Note: highlight consensus pallets, bounty pallets, nfts pallet.

---

Pro tip: use the Rust docs to navigate the SDK!

---

More tips for now:

* Ignore most of the SDK apart from FRAME
* Have a look at examples of other implementations for reference
* Looks at the guides and high level docs

---

Look over FRAME library in Rust docs.

---

## Quest 1: build the shell pallet

```rust
//! # Shell Pallet
//!
//! A bare bones module that contains the minimum requirements for a FRAME pallet to compile.

// We make sure this pallet uses `no_std` for compiling to Wasm.
#![cfg_attr(not(feature = "std"), no_std)]

// Re-export pallet items so that they can be accessed from the crate namespace.
pub use pallet::*;

#[frame_support::pallet]
pub mod pallet {
    // Import various useful types required by all FRAME pallets.
    use super::*;
    use frame_support::pallet_prelude::*;
    use frame_system::pallet_prelude::*;

    // The `Pallet` struct serves as a placeholder to implement traits, methods and calls this
    // pallet exposes.
    #[pallet::pallet]
    pub struct Pallet<T>(_);

    // The pallet's configuration trait.
    #[pallet::config]
    pub trait Config: frame_system::Config {}
}
```

---

## Quest 1: build the shell pallet (steps)

* `cargo new shell-pallet`
* `cargo add frame-system && cargo add frame-support`
* copy paste the shell pallet code
* `cargo build`

---

## Things to do 👀

* Go over pallet parts
* Basic FRAME features to highlight
* Add tests and show mock runtime
* Show coupling with other pallets and why you might want to do that

---

## Quest 2: add functionality

* Add the ability to store a value
* Add events

Note: this may be for after the workshop, time permitting.

---

## Quest 3: use your pallet in a node template

Options:

1. Publish it to a Github repo and add it as a crate to your runtime
2. Add it to the local pallets folder of your node template

---

## Quest 3: use your pallet in a node template (steps)

* Clone the extended parachain template
* Add your pallet to the runtime
* Run `cargo build --release`
* Open the Polkadot JS Apps UI 

---

## Dig deeper into these topics

* FRAME Origins
* Weight system
* Account types and cryptography

---

## Leaving thoughts

* Basic knowledge to start hacking on one of the Polkadot bounties
* FRAME makes it easy to build runtime modules for Substrate chains
* We've barely touched the surface of the capabilities FRAME offers

---

## Questions (maybe for another workshop)

* Where are the runtimes that are live on mainnet?
* How do I know when I can claim a payout from an awarded child bounty on Polkadot?

<!-- 

---

## Extra stuff

Things to note: 

- the mono repo is ___ in size ! cloning it will take a while.. 
```bash
git clone -b polkadot-v1.1.0 --single-branch https://github.com/paritytech/polkadot-sdk.git
```
- don't do `cargo build --release` in the repo workspace!
- the mono repo is made up of substrate, Polkadot and cumulus 


-->

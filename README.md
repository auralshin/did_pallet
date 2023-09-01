# DID Pallet

## Overview

The DID pallet provides functionalities for managing decentralized identifiers (DIDs) within your project's ecosystem, a Web3 infrastructure setting the future of enterprise. With our business banking for the digital era, we offer lightning fast cross-border settlements, fraud-resistant private NFT invoices, and institutional on/off ramps.

This pallet employs a universal identity registry where all necessary data is connected with an address, facilitating the creation of a portable, persistent, privacy-protecting, and personal identity.

Please note: This pallet is intended for learning and evaluation purposes only. It has not been audited and reviewed for production use cases.

## Self-Sovereign Identity

A decentralized or self-sovereign identity provides an innovative approach where the state of your digital identity is owned and controlled by no one but you.

## Benefits of Self-Sovereign Identity

- Seamless Identity Verification
- Non-Custodial Login Solutions
- Stronger Protections for Critical Infrastructure
- Securing the Internet of Things
- Using the Pallet
- Tests - Module tests can be executed with ```cargo test -p did```.

## Identity Identifier -

Any account, whether a key pair or a smart contract, is deemed an account identifier. No registration is needed for an identity.

## Identity Ownership -

Each identity is controlled by a single address. By default, each identity controls itself. More advanced ownership models could be managed through a multi-signature account.

## Delegates -

Delegates are addresses that are delegated for a specific time to perform a function on behalf of an identity. Delegates can be added and revoked using the add_delegate and revoke_delegate functions.

## Attributes -

These attributes can be added and revoked using the add_attribute and revoke_attribute functions.

## Off-chain Attributes -

An identity may need to publish some information off-chain but still requires the security benefits of using a blockchain. This can be done by signing an off-chain transaction with the AttributeTransaction structure and updating it on-chain.

## DID Document -

To create a DID-Document, a DID resolver needs to get all the information from the registry and validate the credentials. DID resolvers are a separate component in the DID stack.

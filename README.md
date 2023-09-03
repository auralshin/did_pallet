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
- Tests - Module tests can be executed with `cargo test -p did`.

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

## Overview

The DID pallet provides functionality for DIDs management.

- Change Identity Owner
- Add Delegate
- Revoke Delegate
- Add Attribute
- Revoke Attribute
- Delete Attribute
- Off-Chain Attribute Management

### Terminology

- **DID:** A Decentralized Identifiers/Identity compliant with the DID standard.
  The DID is an AccountId with associated attributes/properties.
- **Identity Ownership** By default an identity is owned by itself, meaning whoever controls the account with that key.
  The owner can be updated to a new key pair.
- **Delegate:** A Delegate recives delegated permissions from a DID for a specific purpose.
- **Attribute:** It is a feature that gives extra information of an identity.
- **Valid Delegate:** The action of obtaining the validity period of the delegate.
- **Valid Attribute:** The action of obtaining the validity period of an attribute.
- **Change Identity Owner:** The process of transferring ownership.
- **Add Delegate:** The process of adding delegate privileges to an identity.
  An identity can assign multiple delegates for specific purposes on its behalf.
- **Revoke Delegate:** The process of revoking delegate privileges from an identity.
- **Add Attribute:** The process of assigning a specific identity attribute or feature.
- **Revoke Attribute:** The process of revoking a specific identity attribute or feature.
- **Delete Attribute:** The process of deleting a specific identity attribute or feature.

### Dispatchable Functions

- `change_owner` - Transfers an `identity` represented as an `AccountId` from the owner account (`origin`) to a `target` account.
- `add_delegate` - Creates a new delegate with an expiration period and for a specific purpose.
- `revoke_delegate` - Revokes an identity's delegate by setting its expiration to the current block number.
- `add_attribute` - Creates a new attribute/property as part of an identity. Sets its expiration period.
- `revoke_attribute` - Revokes an attribute/property from an identity. Sets its expiration period to the actual block number.
- `delete_attribute` - Removes an attribute/property from an identity. This attribute/property becomes unavailable.
- `execute` - Executes off-chain signed transactions.

### Public Functions

- `is_owner` - Returns a boolean value. `True` if the `account` owns the `identity`.
- `identity_owner` - Get the account owner of an `identity`.
- `valid_delegate` - Validates if a delegate belongs to an identity and it has not expired.
  The identity owner has all provileges and is considered as delegate with all permissions.
- `valid_listed_delegate` - Returns a boolean value. `True` if the `delegate` belongs the `identity` delegates list.
- `valid_attribute` - Validates if an attribute belongs to an identity and it has not expired.
- `attribute_and_id` - Get the `attribute` and its `hash` identifier.
- `check_signature` - Validates the signer from a signature.
- `valid_signer` - Validates a signature from a valid signer delegate or the owner of an identity.
-

## Reference -

Based on : [Substrate Developer Hub](https://github.com/substrate-developer-hub/pallet-did)
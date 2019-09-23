# About Orbs Clients

Orbs Clients are applications that use Orbs Nodes' public HTTP API to interact with smart-contracts on the Orbs blockchain.

## Transaction & Queries

Smart-contract interactions are method calls of on-chain smart-contracts. method calls can be read-only or they can alter the smart-contract state. any read-only method is executed via a Query, while read-write methods are executed as transactions.

Queries can be run locally on Orbs Nodes as opposed to Transactions which must undergo the Orbs Consensus protocol: Helix. 

{% hint style="info" %}
Transactions can still execute read-only smart-contract methods, but using Queries is recommended for optimisation.
{% endhint %}

## Clients vs. Nodes

The Orbs networks is comprised of Nodes and Clients.

Orbs Nodes are running the Helix consensus algorithm and keeping a local state of the entire Orbs blockchain. They receive Queries or Transactions from the Orbs Clients and run the requested operation on their local Orbs blockchain instance.


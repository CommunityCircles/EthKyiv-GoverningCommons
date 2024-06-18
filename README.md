# EthKyiv 2024 - using Circles for Governing the Commons

This readme is written to give you minimal information about Circles to get you up to speed (fast).

## Circles Bounties for EthKyiv 2024

Circles has USD 1400 for two, open-ended bounty tracks for EthKyiv:

1. **Integration track of Circles**: awarded to the best idea of integrating Circles with any existing DeFi, Social apps or protocols,
   SocialFi, ZK protocols, wallets, web2 apps, ... but make sure it is value-aligned ;-)

2. **Governing the Commons with Circles track**: awarded to the best implementation of Group Circles to "govern a common".

Either track requires to use either:
  - Circles v1 on Gnosis Chain mainnet
  - Circles v2 on Chiado testnet
  - or mocked Group Circles (ERC20, or ERC1155): the essense must be that 
    - community currencies have a relevant condition with which people can mint it
      (ie. mocked version of collateralizing their Circles under the same condition)
    - mock and implementation cannot violate core principles of Circles (eg. different issuence)

## A less-short Introduction to Circles

Circles is a social money. At its most basic it is a simple idea: every human should always have
some financial means to facilitate their (digital) life.

If we unpack that mission further though, then in order to fairly distribute such a social money
it reveals a much more challenging problem: how can we determine which accounts belong to
genuine human beings, and which accounts are sybil/bot accounts?

Several projects address such questions in a top-down manner, by creating a registry of which accounts
are authentic. For example, zk-proofs of passports is a great way to achieve this, national governments
already maintain such citizen registries, issue cryptographic documents, and with zk proofs we can assert
properties without revealing all information. Unfortunately not everyone has access to a passport,
and nor should we rely on passports for building identity on the web.

With Circles in contrast, we address this question by turning the global question of "which accounts are sybil",
into a local question of "do you know that the following accounts are *not* sybil?"

To make the money itself local, we have to consider the "fungibility" or "spendability" of Circles:
there isn't one (global) Circles where everyone has their balance,
Circles instead are defined on each node of a social graph, locally. For Alice to be able to spend
her Circles balance to Bob we need to search over this graph for an available and sufficient flow from Alice to Bob.

This graph we've talked about is a social graph. Vertices on this graph are the account of people that registered.
Edges on this graph are directed and are created everytime one person attests to **trust** the account of another person
(to not be sybil).

Issuance of Circles is set by a simple rule: every person can issue one Circle (CRC) per hour to their own account,
that is, they can issue it at their location on the graph. When two people mutually assert they trust each other,
the trust edges are interpreted as a flow edge: both people consider their own local Circles equivalent, or fungible
with the Circles of the other person, so their balances can be exchanged one for one by the protocol. Transitively,
combining a path of flow edges, Circles can now flow from one sender to another person or organization outside of either's circle of trust.

In effect, the local Circles become path-fungible, meaning that if a path between two people exists, they can send Circles to eachother,
while preserving that all Circles remain local to where they were issued. This brings us "full circle": Circles as a protocol
is agnosistic whether accounts are sybil or not, because every authentic human who only trusts other authentic accounts is shielded
from the behaviour of other sybil accounts (outside of their local Circle), while still having a global reach to spend over the whole graph.

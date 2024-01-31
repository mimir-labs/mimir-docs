# 💰 Multisig Introduction

&#x20;A multisig is composed of one or more addresses and a threshold. The threshold defines how many signatories (participating addresses) need to agree on submitting an extrinsic for the call to be successful.

For example, Alice, Bob, and Charlie set up a multisig with a threshold of 2. This means Alice and Bob can execute any call even if Charlie disagrees with it. Likewise, Charlie and Bob can execute any call without Alice. A threshold is typically a number smaller than the total number of members but can also be equal to it, which means they all have to agree.

Multi-signature accounts have several uses:

* Securing your stash: use additional signatories as a 2FA mechanism to secure your funds. One signer can be on one computer, and another can be on another or in cold storage. This slows down your interactions with the chain but is orders of magnitude more secure.
* Board decisions: legal entities such as businesses and foundations use multisigs to govern over the entity's treasury collectively.
* Group participation in governance: a multisig account can do everything a regular account can. A multisig account could be a council member in Kusama's governance, where a set of community members could vote as one entity.

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

**Reference**

{% embed url="https://wiki.polkadot.network/docs/learn-account-multisig" %}

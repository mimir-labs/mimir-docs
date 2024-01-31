# 💳 Accounts



{% hint style="info" %}
Mimir aims to be the launcher for users in the Polkadot ecosystem, therefor Mimir's account design is more aligned with the Polkadot ecosystem. Unlike Safe, extension wallets and multisig wallets will be on the same level in Mimir.&#x20;

Once a user selects an account, all subsequent transactions and application accesses will be conducted under that account as the main entity.
{% endhint %}

**Currently, the account entities we support include: Extension Account, Static Multisig, and Flexible Multisig.**

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

## 1. Extension

Mimir allows interactions with all single-signature accounts in the Polkadot ecosystem extension wallets. Currently, we support [Polkadot.js](https://polkadot.js.org/extension/), [Subwallet](https://www.subwallet.app/download.html), and [Talisman](https://www.talisman.xyz/download). All accounts in the extension wallets authorized by the user will be displayed under the Extension Wallet section.&#x20;

Users can access applications in Dapps using this wallet and interact with them using the extension wallet as the main entity.&#x20;

Some quick operations, such as transfers, can also be easily completed.

## 2. Multisig

In Mimir, multisig accounts are currently offered in two forms: Static Multisig and Flexible Multisig. They share some common rules:

1. Mimir supports multisig wallets as members of another multisig, which can greatly expand the real-world business scenarios of multisig.
2. The created multisig is visible to all multisig members (including members of nested multisigs).
3. If a member user needs to operate on a particular multisig (including initiating and approving transactions), please select that multisig in the account options.

### 2.1 Account Visibility

<figure><img src="../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

A, as a multisig account, wants to send 10$DOT to B. C is a multisig composed of E and F, and A is a multisig composed of C and D. E, F, and D are all single-signature accounts.

If the user holds accounts E or F, after logging into Mimir, they can enter multisigs A and C.&#x20;

If the user holds account D, after logging into Mimir, they can enter multisig C.

### 2.2 Static Multisig

Static Multisig is generated based on the Multisig Pallet, which is a native Pallet of Substrate.&#x20;

**Its advantages are:**&#x20;

1. During the creation process, users do not need to pay any fees.
2. It only needs to be created once and can be shared across the entire Polkadot ecosystem.
3. Users will get the same address as long as they create it based on the same threshold and members.&#x20;

**Its disadvantage is:**&#x20;

1. Once created, the members and threshold cannot be changed.

**Reference:**&#x20;

{% embed url="https://wiki.polkadot.network/docs/learn-account-multisig" %}

### 2.3 Flexible Multisig

Flexible Multisig is an account type formed by the combination of the Proxy Pallet and the Multisig Pallet. Essentially, it is a Pure Proxy with only one Static Multisig acting as its proxy.&#x20;

**Its advantages are:**

1. After successful creation, users can still modify members and thresholds (with the agreement of members reaching the threshold).
2. Even with the same members and thresholds, different multisig addresses can be obtained.&#x20;

**Its disadvantages are:**

1. Multiple transactions are required during the creation process, and a certain Reserve Fund needs to be prepared.
2. Each creation is only effective in the currently selected network

###

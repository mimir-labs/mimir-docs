# 🏧 Transaction

{% hint style="info" %}
Approval processing for multisig transactions and historical records will all be conducted in the Transaction Section.
{% endhint %}

## 1. Authority

Due to the inherent mechanism of multisig, all multisig members have transaction approval permissions for that multisig.&#x20;

If there are nested multisigs, then the members of the lower-level multisig also have transaction approval permissions for the highest-level multisig.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

### Initiator

Given this setup, if there's a desire to initiate a transaction from A to B transferring 10 $DOT, any of the single-signature accounts E, F, or D can act as the initiator for this transaction.

To initiate this transaction, holders of E, F, and D need to select and enter the A account. Then, they can initiate the transfer transaction and set themselves as the Initiator to start the approval process for this transaction.

> The Multisig Pallet requires that when initiating a multisig transaction, a portion of funds must be locked. These funds will be returned once the transaction is successfully executed or cancelled. On the Polkadot network, the requirement is **20 $DOT**, while on the Kusama network, it's **0.2 $KSM**.

### Approver

If the transaction is initiated by D, then both E and F can act as Approvers to agree and execute this transaction.

Both E and F need to select the A account as the operating account in order to view this transaction. After that, they can choose themselves as the Approver to approve the transaction.

### Canceller

If the transaction is initiated by D, then E and F can only choose to either approve or ignore the transaction. Only D has the authority to cancel this transaction.

## 2. Transaction Details

Currently, Mimir only supports the parsing of transactions initiated through Mimir. Therefore, we recommend that you and your members use Mimir as the multisig transaction tool to ensure smooth completion of transactions.

Transaction details include:

1. The current approval status of the transaction.
2. The content of the transaction (e.g., how much money was transferred to whom, how much $DOT was staked for a particular node, etc.)
3. Transaction-related parameters including Tx hash, Call Hash and Call Data.

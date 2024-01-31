# 🛠 Initiate Transactions

{% hint style="info" %}
When initiating a transaction, switch to the desired account. Transactions initiated in Mimir using the Extension Wallet, which interact via the extension and don't require approval, won't be detailed here.&#x20;

The focus will be on initiating a transaction with a multisig account.
{% endhint %}

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

To illustrate, let's use a transfer transaction as an example.

1. Ensure you've selected the multisig account you want to use for the transfer.
2. Use the Transaction Dapp in the application to make the transfer. Enter the amount and recipient.

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

3. Choose a local Extension Wallet that's a member of the multisig as the transaction initiator.

{% hint style="info" %}
The Multisig Pallet requires funds to be locked during multisig transactions. These funds are returned after the transaction succeeds or is canceled. It's $20 DOT on the Polkadot network and $0.2 KSM on the Kusama network.
{% endhint %}

After clicking 'confirm' and signing in the extension, the transaction initiation is complete.

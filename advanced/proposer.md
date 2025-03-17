# 🗣️ Proposer

**Proposer** is a role newly introduced by Mimir for multisig accounts, specifically for initiating transaction proposals, but it cannot directly approve or reject transactions.

Once a proposal is submitted:

* **If any member approves it,** the transaction will proceed through the normal execution process.
* **If any member rejects it,** the transaction will be voided and will not be executed.

{% hint style="info" %}
Members can also be proposers at the same time.
{% endhint %}

## Set a Proposer

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Click "Setting" on homepage. Both the ⚙️ beside name and Setting in side bar are ok.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

Scroll down and you will find Proposer setting.

<figure><img src="../.gitbook/assets/image (28).png" alt="" width="375"><figcaption></figcaption></figure>

Follow the guide to finish setting:

1. Proposer: The address you want to be the proposer of your multisig.
2. Signer: Select the memeber you want to sign the message(It's not a transaction).

## Submit a transaction propose

Keep proposer account connected and select the multisig account proposer can manage.

Proposer can submit any transactions as memebers do, whatever it's a third-party app/batch transaction/template transactions.

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

The proposer only needs to select corresponding permission when signing.

It is not a transaction as well.

## Handle propose

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

Transactions initiated by a proposer will be displayed in the **Pending** page in the format shown above.

At this stage, further action is required from the members.

Once a member approves, the transaction will proceed through the normal multisig process.

## Other Features

In addition to Members, Proposers can also use the Batch API to submit transactions to Mimir.

If you want to reduce the risk of a Member's private key being compromised, you can use a new account as a Proposer to utilize the Batch API functionality. Since Proposer don't have to submit transactions, no funds are required.

Batch API Detail:

{% content-ref url="../developer/batch-api.md" %}
[batch-api.md](../developer/batch-api.md)
{% endcontent-ref %}

# ⚖️ Manage Transactions

After accessing the Transaction page, users can view the list of pending transactions for the selected account in the Pending section.

All members can view the transaction details and progress, and decide how to handle it.

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

## Function

### Approve

Agree to execute the transaction and choose an Approver from the local wallet.&#x20;

The 'Approve' button remains clickable until the last local Approver also agrees to the transaction.

### Cancel

If you initiated the transaction, you can choose to cancel it. Once canceled, it moves to the 'History' and others can't approve it anymore.

### Restore

<figure><img src="../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

If this transaction was initiated through another application, you can enter the Call Data to restore the transaction.

## Information

### Process

The 'Process' section shows the current progress of the transaction, displaying the approval status of multisig members.&#x20;

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

If this transaction involves nested multisig accounts, users can click on "overview" to view the details.

### Transaction

It includes the specific details of the transaction, the method called, and its parameters.

### Call Information

It contains the transaction's Call Hash, Call Data, and initiating Tx Hash. Users can verify the transaction using third-party tools.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

If this transaction is part of a nested multisig hierarchy, users can also view the final execution address.

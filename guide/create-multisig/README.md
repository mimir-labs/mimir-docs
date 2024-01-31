# 🟢 Create Multisig

After entering Mimir, you can create a multisig wallet. If you don't create one at the beginning, you can also create it later under the account selection.

## Static Multisig

Please fill in the following basic information to proceed with the creation:&#x20;

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

**Multisig Name:** All multisig members will see this name.&#x20;

**Multisig Members:** Members that make up this multisig. You can directly copy the address and click 'Add' to include them. If the member is already in your address book, you can directly click the plus sign to add.&#x20;

{% hint style="info" %}
Note: Please ensure that the multisig members include at least one of your local Extension Wallets; otherwise, the creation cannot be completed.&#x20;
{% endhint %}

**Multisig Threshold:** The number of approvals required for a transaction to be executed.



If you only fill in the above information and keep the Flexible Multisig switch turned off, you will create a Static Multisig based on the Multisig Pallet, and its members and threshold cannot be changed.&#x20;

## Flexible Multisig

If you turn on the Flexible Multisig switch, you will create a multisig that allows for modifications to its members and threshold.

Before completing the creation, you need to execute two transactions as prompted to finalize the creation:

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

1. Create a Flexible Multisig address.

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

2. Set members. Please ensure that you complete the above two transactions; otherwise, the creation will not be successful.

{% hint style="info" %}
Note: During the creation process, make sure that the Extension Wallet used for creation has a sufficient balance to cover the amount required to be locked according to the Pallet.
{% endhint %}

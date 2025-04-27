# 🚛 Transaction Simulation

Chopsticks is a transaction simulation tool developed by Acala. It allows you to locally simulate a transaction execution and provides the resulting output.

We recommend performing a transaction simulation both **when initiating a multisig transaction** and **when the last member approves it**.

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

By running a simulation, you can:

1. Verify whether the transaction will execute successfully. If the transaction is likely to fail, further execution can be avoided, preventing unnecessary gas fees.
2. Ensure the transaction result matches expectations. If the outcome is different from what was intended, consider reconstructing the transaction and verifying frontend security before proceeding.


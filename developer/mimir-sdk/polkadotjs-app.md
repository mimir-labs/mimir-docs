# PolkadotJS App

### Integration For PolkadotJs

Follow these steps to integrate your application with Mimir:

#### 1. Inject SDK into Your Application

Substrate-based wallets inject an object into `window.injectedWeb3` for interaction. Mimir follows this approach but uses an iframe, so direct injection into the window object isn't possible. Instead, use the provided npm package for injection.

**Check if Opened in an Iframe**

First, determine if the application is opened within an iframe:

```
const openInIframe = window !== window.parent;
```

**Check if Opened in Mimir's Iframe**

Use the following function to check if the application is opened within Mimir's iframe:

```
import { inject, isMimirReady, MIMIR_REGEXP } from '@mimirdev/apps-inject';

const origin = await isMimirReady();

if (!origin) {
  // Not opened in Mimir
  return;
}

// Verify if the URL matches Mimir's pattern
if (MIMIR_REGEXP.test(origin)) {
  // Inject Mimir into window.injectedWeb3
  inject();
  // Now you can use polkadot extension functions
}
```

#### 2. Retrieve the Multisig Account

Mimir implements the same interface as [polkadot-js/extension](https://github.com/polkadot-js/extension), allowing you to obtain multisig accounts similarly to other plugin wallets.

**Example Code**

Use the following code snippet to obtain the multisig account:

```
import { web3Accounts, web3Enable } from '@polkadot/extension-dapp';

const injected = await web3Enable('your app name');
const accounts = await web3Accounts();
```

#### 3. Sign and Send Transactions

To send a `transferKeepAlive` transaction using Mimir's multisig account, follow these steps:

**Example Code (for @polkadot/api >= v15.0.1)**

```
import { web3FromSource } from '@polkadot/extension-dapp';
import { checkCallAsync } from '@mimirdev/apps-sdk';

// ... existing code ...

const injected = await web3FromSource(source);

assert(injected, `Unable to find a signer for ${address}`);

const isMimir = injected.name === 'mimir'

let tx = api.tx.balances.transferKeepAlive();

// ⚠️Note withSignedTransaction is required
tx.signAndSend(injected.signer, { signer: injected.signer, withSignedTransaction: true }, (results) => {
  console.log(results);
});
```

**Example Code (for @polkadot/api < v15.0.1)**

```
import { web3FromSource } from '@polkadot/extension-dapp';
import { checkCallAsync } from '@mimirdev/apps-sdk';

// ... existing code ...

const injected = await web3FromSource(source);

assert(injected, `Unable to find a signer for ${address}`);

const isMimir = injected.name === 'mimir'

let tx = api.tx.balances.transferKeepAlive();

// ⚠️Note that the following logic will only be executed when injected.name === 'mimir'.
if (isMimir) {
  const result = await injected.signer.signPayload({
    address: address,
    method: tx.method.toHex(),
    genesisHash: api.genesisHash.toHex()
  });

  // Retrieve the method returned by Mimir.
  const method = api.registry.createType('Call', result.payload.method);

  // check the original transaction's call, after being wrapped by `AsMulti`, is matches the tx call
  // `address` is get from mimir wallet
  // ⚠️Note: this is not required if you trust mimir
  if (!(await checkCallAsync(api, method, result.payload.address, tx.method, address))) {
    throw new Error('not safe tx');
  }

  // Reconstruct a new tx.
  tx = api.tx[method.section][method.method](...method.args);

  // add signature to tx
  tx.addSignature(result.signer, result.signature, result.payload);
}

tx.send();
```

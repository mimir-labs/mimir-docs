# Polkadot API(PAPI)

### Integration For PAPI

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

#### 2. Retrieve the pjs-signer

You can easily get the polkadotSigner from the extension, similar to how it's done in the [PAPI documentation](https://papi.how/signers#from-a-browser-extension)

```
import {
  getInjectedExtensions,
  connectInjectedExtension,
} from "polkadot-api/pjs-signer"

// Connect to an extension
const selectedExtension: InjectedExtension = await connectInjectedExtension('mimir')

// Get accounts registered in the extension
const accounts: InjectedPolkadotAccount[] = selectedExtension.getAccounts()

// The signer for each account is in the `polkadotSigner` property of `InjectedPolkadotAccount`
const polkadotSigner = accounts[0].polkadotSigner
```

#### 3. Sign and Send Transactions

Once you have the polkadotSigner, you can use it to sign and send transactions. Here's an example using PAPI (version >= 0.9.1):

> **Note**: For PAPI versions below 0.9.1, Mimir cannot be used to send transactions. Please upgrade to PAPI version 0.9.1 or higher to use Mimir's transaction signing capabilities. Also, please read [this PR](https://github.com/polkadot-js/api/pull/5920) for important changes to the transaction signing process.

Here's an example using PAPI version 0.9.1 or higher:

```
import { createClient } from "polkadot-api"
import { wnd } from "@polkadot-api/descriptors"
import { chainSpec } from "polkadot-api/chains/westend2"
import { getSmProvider } from "polkadot-api/sm-provider"
import { start } from "polkadot-api/smoldot"

// create the client with smoldot
const smoldot = start()
const client = createClient(getSmProvider(smoldot.addChain({ chainSpec })))

// get the safely typed API
const api = client.getTypedApi(wnd)

// create the transaction sending some assets
const transfer = api.tx.Balances.transfer_allow_death({
  dest: 'dest address',
  value: 12345n,
})

// sign and submit the transaction while looking at the
transfer.signAndSubmit(polkadotSigner);
```

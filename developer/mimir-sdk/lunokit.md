# LunoKit

### React Library for Polkadot Wallet Connections

LunoKit provides a unified wallet connection infrastructure for Polkadot ecosystem, with built-in support for Mimir multisig wallets.

### Integration For LunoKit

#### 1. Install LunoKit Packages

First, install the required LunoKit packages:

```bash
npm i @luno-kit/react @luno-kit/ui @tanstack/react-query
```

#### 2. Configure Mimir Connector

Set up LunoKit with Mimir connector in your application:

```tsx
import { LunoKitProvider, ConnectButton } from '@luno-kit/ui'
import { createConfig } from '@luno-kit/react'
import { kusama, polkadot } from '@luno-kit/react/chains'
import { mimirConnector } from '@luno-kit/react/connectors'
import '@luno-kit/ui/styles.css'

const config = createConfig({
  appName: 'Mimir Example',
  chains: [polkadot, kusama],
  connectors: [mimirConnector()],
  autoConnect: true,
})

function App() {
  return (
    <LunoKitProvider config={config}>
      <ConnectButton />
    </LunoKitProvider>
  )
}
```

#### 3. Connect to Mimir Wallet

Once configured, users can connect their Mimir multisig wallets through the LunoKit interface, which provides a unified experience across different wallet types.

### More about LunoKit

Guide: [https://docs.lunolab.xyz/](https://docs.lunolab.xyz/)

Website: [https://www.lunolab.xyz/](https://www.lunolab.xyz/)

Github: [https://github.com/Luno-lab/LunoKit](https://github.com/Luno-lab/LunoKit)

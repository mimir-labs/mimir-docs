# 🖥️ Mimir SDK

If you are interested in integrating your application with Mimir, please refer to the following documentation and feel free to contact us for further assistance.

{% embed url="https://github.com/mimir-labs/mimir-apps-sdk" %}

## Add to existing apps

To integrate the apps with Mimir, it needs to be opened within Mimir's built-in web page (iframe) and requires the use of Mimir's injected library to inject Mimir's account. Therefore, for the apps, Mimir's multisig account can be used in the same way as the accounts in the extension wallet, such as [polkadot-js/extension](https://github.com/polkadot-js/extension).

## Introduction

Integrating your application with Mimir requires it to be opened within Mimir's built-in web page (iframe) and utilize Mimir's injected library to access Mimir's account. This integration allows your application to use Mimir's multisig account similarly to accounts in the extension wallet, such as [polkadot-js/extension](https://github.com/polkadot-js/extension).

### Installation

To integrate Mimir into your application, install the necessary packages using either `yarn`, `pnpm` or `npm`:

#### Using Yarn

```
yarn add @mimirdev/apps-inject
```

#### Using NPM

```
npm install @mimirdev/apps-inject
```

#### Using PNPM

```
pnpm add @mimirdev/apps-inject
```

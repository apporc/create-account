Create Account Library
=======

This library allows you to prompt the user to create and initialize an account using Anchor.

## Installation

The `@greymass/create-account` package is distributed as a module on [npm](https://www.npmjs.com/package/@greymass/create-account).

```
yarn add @greymass/create-account
# or
npm install --save @greymass/create-account
```

## Usage

This function will automatically open a popup window prompting the user to buy an account. Once the payment is received,
the account will be redirected to Anchor with an account creation code. Anchor is then expected to send a confirmation or
error message back before sending the user back to the defined url.

```
import { AccountCreator } from '@greymass/create-account';

// Initialize the account creator object
const accountCreator = new AccountCreator({
  supportedChains: [], // List of supported chains.
  scope: 'wallet', // A string representing the scope of the account creation.
  returnUrl: 'http://wallet.greymass.com', // Url to return the user to once the account is created.
})

// Open a popup window prompting the user to create an account.
accountCreator.createAccount().then((creationResult) => {
  // Handle success, the creationResult will be an esr callback object.
}).catch((error) => {
  // Handle error
})
```

## Developing

You need [Make](https://www.gnu.org/software/make/), [node.js](https://nodejs.org/en/) and [yarn](https://classic.yarnpkg.com/en/docs/install) installed.

Clone the repository and run `make` to checkout all dependencies and build the project. See the [Makefile](./Makefile) for other useful targets. Before submitting a pull request make sure to run `make lint`.

---

Made with ☕️ & ❤️ by [Greymass](https://greymass.com), if you find this useful please consider [supporting us](https://greymass.com/support-us).

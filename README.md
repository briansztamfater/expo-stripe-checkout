### expo-stripe-checkout

Inspired by (https://github.com/catalinmiron/react-native-plaid-link)

Since currently the only way to implement Stripe Checkout on an Expo app is by ejecting, I've built this lib that adds support for Stripe Checkout using a WebView.

![expo-stripe-checkout-demo](expo-stripe-checkout-demo.gif)

### Usage

```
npm install expo-stripe-checkout
```
or
```
yarn add expo-stripe-checkout
```

#### API

| Prop                                                                       | Type       | defaultValue          |
| -------------------------------------------------------------------------- | ---------- | --------------------- |
| **publicKey** (required)                                                   | `string`   |                       |
| **amount** (required)                                                      | `number`   |                       |
| **imageUrl** (required)                                                    | `string`   |                       |
| **storeName** (required)                                                   | `string`   |                       |
| **description** (required)                                                 | `string`   |                       |
| **allowRememberMe** (required)                                             | `boolean`  |                       |
| **storeName** (required)                                                   | `string`   |                       |
| **onPaymentSuccess** (required)                                            | `function` |                       |
| **onClose** (required)                                                     | `function` |                       |
| currency                                                                   | `string`   | `USD`                 |
| prepopulatedEmail                                                          | `string`   |                       |
| style                                                                      | `ViewStyle`|                       |

```js
render() {
  return <StripeCheckout
    publicKey="sk_test_4eC39HqLyjWDarjtT1zdp7dc"
    amount={100000}
    imageUrl="https://pbs.twimg.com/profile_images/778378996580888577/MFKh-pNn_400x400.jpg"
    storeName="Stripe Checkout"
    description="Test"
    currency="USD"
    allowRememberMe={false}
    prepopulatedEmail="test@test.com"
    onClose={this.onClose}
    onPaymentSuccess={this.onPaymentSuccess}
  />
}

onPaymentSuccess = (token) => {
  // send the stripe token to your backend!
}

onClose = () => {
  // maybe navigate to other screen here?
}
```

For more information please
[read their docs](https://stripe.com/docs/checkout)

#### Questions?

Feel free to contact me:

Twitter: [@briansztamfater](http://twitter.com/briansztamfater)
Medium: [http://medium.com/@briansztamfater](http://medium.com/@briansztamfater)

---

PaymentsAPI

# Interface: PaymentsAPI

Defined in: figmaPluginTypes.ts:2106

## See

https://www.figma.com/plugin-docs/api/figma-payments

## Properties

### status

> `readonly` **status**: [`PaymentStatus`](../type-aliases/PaymentStatus.md)

Defined in: figmaPluginTypes.ts:2133

An object describing the user’s payment status. Right now, the only
attribute on this object is whether the user has paid. In the future, we
might add more attributes here to provide more information.

```ts
type PaymentStatus = {
  type: "UNPAID" | "PAID" | "NOT_SUPPORTED";
};
```

A status type of `NOT_SUPPORTED` indicates that an internal error has occurred
and the user's payment status could not be determined at that time. Plugins
should treat `NOT_SUPPORTED` as an error and not grant access to paid features.

In development, you’ll be able to test out the entire checkout flow without
having to input any actual payment information. Doing so will update your
payment status accordingly. Any changes to payment status in development is
local and not persisted, and will be reset when restarting your client or
using a different machine.

Note: To test out your plugin or widget with payment statuses other than `UNPAID`
while developing, use the [PaymentsAPI.setPaymentStatusInDevelopment](#setpaymentstatusindevelopment)
function.

For published resources, this always returns `PAID` for the creator.

## Methods

### getPluginPaymentTokenAsync()

> **getPluginPaymentTokenAsync**(): `Promise`\<`string`\>

Defined in: figmaPluginTypes.ts:2212

This method generates a token that can be used to securely communicate the
identity of the current user on the current plugin or widget. You can
provide its returned value as the `plugin_payment_token` query parameter to
the [payments REST API](https://www.figma.com/developers/api#payments) endpoint.

#### Returns

`Promise`\<`string`\>

---

### getUserFirstRanSecondsAgo()

> **getUserFirstRanSecondsAgo**(): `number`

Defined in: figmaPluginTypes.ts:2150

When the plugin was first run by the current user.

This is defined as the number of seconds since the current user ran the
plugin or widget for the first time. This will return 0 the very first time
a user runs your plugin, and will always return 0 when running a plugin in
development.

#### Returns

`number`

---

### initiateCheckoutAsync()

> **initiateCheckoutAsync**(`options?`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:2190

This triggers a checkout flow in the Figma UI for the user to purchase your
plugin or widget. The user will be prompted to enter their payment
information and purchase your resource. This function resolves either when
the user has completed the checkout flow, or they’ve dismissed it.

Warning: This function will throw an exception in certain cases:

1. While in query mode and accepting plugin parameters.
2. During widget rendering. Instead, put calls to this function inside your widget event handlers.

See [our guide](https://www.figma.com/plugin-docs/requiring-payment#when-to-call-initiatecheckoutasync) for more information.

This function takes an `options` argument that controls the behavior of the
checkout flow.

```ts
type CheckoutOptions = {
  // This option controls the behavior and copy of the
  // interstitial checkout modal.
  //
  // * PAID_FEATURE:  This is the default. Use this option if
  //                  you're asking the user to pay for a
  //                  certain premium feature.
  //
  // * TRIAL_ENDED:   Use this option if the user's free trial
  //                  has ended.
  //
  // * SKIP:          Use this option if you want to skip the
  //                  interstitial entirely. This is useful if
  //                  you have your own upgrade CTA in your
  //                  plugin's UI.
  interstitial?: "PAID_FEATURE" | "TRIAL_ENDED" | "SKIP";
};
```

After `initiateCheckoutAsync` resolves, use `figma.payments.status` to check
the user’s payment status.

#### Parameters

##### options?

###### interstitial?

`"PAID_FEATURE"` \| `"TRIAL_ENDED"` \| `"SKIP"`

#### Returns

`Promise`\<`void`\>

---

### requestCheckout()

> **requestCheckout**(): `void`

Defined in: figmaPluginTypes.ts:2205

This is useful for [text review plugins](https://www.figma.com/plugin-docs/textreview-plugins). Since these
plugins can only run in query mode, they cannot call
`initiateCheckoutAsync` while a user is editing text as that will throw an
exception.

if you are building a text review plugin, call `requestCheckout` to
indicate that the user needs to checkout in order to continue using the
plugin. When the user exits text editing, they will be prompted to
checkout. If the user dismisses the checkout flow, the text review plugin
will automatically be disabled.

#### Returns

`void`

---

### setPaymentStatusInDevelopment()

> **setPaymentStatusInDevelopment**(`status`): `void`

Defined in: figmaPluginTypes.ts:2141

Warning: This method can only be used in development.

This sets your payment status to the value of the `status` argument in this
method. This is a global setting that will impact your payment status for
all plugins or widgets you run in development.

#### Parameters

##### status

[`PaymentStatus`](../type-aliases/PaymentStatus.md)

#### Returns

`void`

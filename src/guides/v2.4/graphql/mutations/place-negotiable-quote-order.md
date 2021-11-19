---
group: graphql
title: placeNegotiableQuoteOrder mutation
---

The `placeNegotiableQuoteOrder` mutation converts the cart into an order and returns an order ID. You cannot manage orders with GraphQL, because orders are part of the backend. You can use REST or SOAP calls to manage orders to their completion.

Perform the following actions before using the `placeNegotiableQuoteOrder` mutation:

-  Create an empty cart
-  Add one or more products to the cart
-  Set the billing address
-  Set the shipping address
-  Set the shipping method
-  Set the payment method

## Syntax

```graphql
mutation {
  placeNegotiableQuoteOrder(
    input: PlaceNegotiableQuoteOrderInput
  ) {
    PlaceNegotiableQuoteOrderOutput
  }
}
```

## Example usage

**Request:**

```graphql

```

**Response:**

```json

```

## Input attributes

The `PlaceNegotiableQuoteOrderInput` object must contain the following attribute:

Attribute |  Data Type | Description
--- | --- | ---
`quote_uid` | String! | The unique ID of a `NegotiableQuote` object

## Output attributes

The `placeOrderOutput` object returns an `order` object.

Attribute |  Data Type | Description
--- | --- | ---
`order` | Order! | Contains the generated order number

### Order object

Attribute |  Data Type | Description
--- | --- | ---
`order_number` | String | The unique ID that identifies the order

## Errors

Error | Description
--- | ---
`Enter a valid payment method and try again` | The payment method was not set. See [setPaymentMethodOnCart]({{ page.baseurl }}/graphql/mutations/set-payment-method.html) mutation.
`Guest email for cart is missing.` | The guest attempted to place an order but did not provide an email address. See [setGuestEmailOnCart]({{ page.baseurl }}/graphql/mutations/set-guest-email.html) mutation.
`Please check the billing address information` | The billing address was not set. See [setBillingAddressOnCart]({{ page.baseurl }}/graphql/mutations/set-billing-address.html) mutation.
`Required parameter "cart_id" is missing` | The mutation does not contain a `cart_id` parameter.
`Some addresses can't be used due to the configurations for specific countries` | The shipping method was not set. See [setShippingMethodsOnCart]({{ page.baseurl }}/graphql/mutations/set-shipping-method.html) mutation.
`Some of the products are out of stock` | One of the products in the shopping cart are currently out of stock.
`The current user cannot perform operations on cart` | An unauthorized user (guest) tried to place an order on behalf of an authorized user (customer), or a customer tried to place an order on behalf of another customer.
`The shipping method is missing. Select the shipping method and try again` | The shipping method was not set. See [setShippingMethodsOnCart]({{ page.baseurl }}/graphql/mutations/set-shipping-method.html) mutation.
`Unable to place order: A server error stopped your order from being placed. Please try to place your order again` | The shopper tried to place an order when no products are in the shopping cart.

---
group: graphql
title: removeRewardPointsFromCart mutation
ee_only: True
redirect_to: https://developer.adobe.com/commerce/webapi/graphql/schema/cart/mutations/remove-reward-points/
status: migrated
---

The `removeRewardPointsFromCart` mutation removes all reward points that were previously applied to the customer's cart with the [`applyRewardPointsToCart` mutation]({{page.baseurl}}/graphql/mutations/apply-reward-points.html).

## Syntax

`mutation: removeRewardPointsFromCart(cartId: ID!): RemoveRewardPointsFromCartOutput`

## Example usage

The following example removes all reward points from the customer's cart. The `applied_rewards_points` object is now null.

**Request:**

```graphql
mutation {
  removeRewardPointsFromCart(cartId: "8k0Q4MpH2IGahWrTRtqM61YV2MtLPApz")
  {
    cart {
      applied_reward_points {
        money {
          currency
          value
        }
        points
      }
      prices {
        applied_taxes {
          amount {
            currency
            value
          }
        }
        grand_total {
          currency
          value
        }
      }
    }
  }
}
```

**Response:**

```json
{
  "data": {
    "removeRewardPointsFromCart": {
      "cart": {
        "applied_reward_points": null,
        "prices": {
          "applied_taxes": [
            {
              "amount": {
                "currency": "USD",
                "value": 6.93
              }
            }
          ],
          "grand_total": {
            "currency": "USD",
            "value": 90.93
          }
        }
      }
    }
  }
}
```

## Input attributes

The `removeRewardPointsFromCart` mutation requires the `cart_id` attribute.

Attribute | Data Type | Description
--- | --- | ---
`cart_id` | String! | The unique ID that identifies the customer's cart

## Output attributes

The `RemoveRewardPointsFromCartOutput` object contains the `Cart` object.

Attribute |  Data Type | Description
--- | --- | ---
`cart` |[Cart!](#CartObject) | Describes the contents of the specified shopping cart

### Cart object {#CartObject}

 {% include graphql/cart-object-24.md %}

[Cart query output]({{page.baseurl}}/graphql/queries/cart.html#cart-output) provides more information about the `Cart` object.

## Errors

Error | Description
--- | ---
`Could not find a cart with ID \"xxxxx\"` | The ID provided in the `cart_id` field is invalid or the cart does not exist for the customer.
`The cart isn't active` | The cart with the specified cart ID is unavailable, because the items have been purchased and the cart ID becomes inactive.
`Field removeRewardPointsFromCart.cart_id of required type String! was not provided` | The value specified in the `removeRewardPointsFromCart.cart_id` argument is empty.

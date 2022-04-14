# Order Placed

### 

## Javascript Code
```js
window.appEventData = window.appEventData || [];
appEventData.push({
  "event": "Order Placed",
    "cart": {
        "cartID": "<cartID>"
    },
    "transaction": {
        "item": [
            {
                "altPersonPickUp": <altPersonPickUp>,
                "fulfillment": {
                    "method": "<method>",
                    "source": "<source>",
                    "storeID": "<storeID>"
                },
                "price": {
                    "sellingPrice": "<sellingPrice>"
                },
                "productInfo": {
                    "productID": "<productID>"
                },
                "quantity": <quantity>,
                "voucherDiscount": {
                    "orderLevelDiscountAmount": "<orderLevelDiscountAmount>",
                    "orderLevelDiscountCode": "<orderLevelDiscountCode>"
                }
            }
        ],
        "payment": [
            {
                "loyaltyPointsAmount": <loyaltyPointsAmount>,
                "paymentAmount": "<paymentAmount>",
                "paymentGateway": "<paymentGateway>",
                "paymentID": "<paymentID>",
                "paymentMethod": "<paymentMethod>"
            }
        ],
        "profile": {
            "address": {
                "country": "<country>",
                "postalCode": "<postalCode>"
            }
        },
        "purchaseID": "<purchaseID>",
        "total": {
            "currency": "<currency>",
            "numPayments": <numPayments>,
            "revenue": "<revenue>"
        }
    }
});
```

## Variable Definitions

|Path|Type|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|cart.cartID|string|Back-end identifier for a shopping cart|12345, 435678, 34567, XCV456, XCV876|||||||
|transaction.item[n].altPersonPickUp|integer|When a user has put in the information of an alternate pick up person during the checkout process.||||||||
|transaction.item[n].fulfillment.method|string|Describes the method of fulfillment|Shipped, Emailed, Pick Up In Store, Will Call|||||||
|transaction.item[n].fulfillment.source|string|Describes the entity responsible for fulfillment. Uasge is flexible.|Vendor:xyz, Store:43567, Email:system3, Warehouse:7865|||||||
|transaction.item[n].fulfillment.storeID|string|A unique identifier for the store that the order was placed with.|stew's boot shop, kat's cat toys, 12345|||||||
|transaction.item[n].price.sellingPrice|string|String representation of the price paid after coupons or discounts. Positive. Up to two decimal places for cents. No currency symbol.|200, 29.99, 50, 0|^[0-9]*(\.[0-9]{1,2})?$||||||
|transaction.item[n].productInfo.productID|string|Unique Identifier of a product or offering.  Must match the format of back-end systems if used as a key for import of product meta data. Most often, one level above SKU for products with SKU variants. |155, 65588, 987764448|||||||
|transaction.item[n].quantity|integer|Integer number of products being acted upon \(added to a cart, removed from wishlist, purchased, reserved\)|1, 2, 3, 4, 5||||1|||
|transaction.item[n].voucherDiscount.orderLevelDiscountAmount|string|String representation of an order level discount applied to an item in a transaction. Positive. Up to two decimal places for cents. No currency symbol.|5, 20, 10.22, 19.2|^[0-9]*(\.[0-9]{1,2})?$||||||
|transaction.item[n].voucherDiscount.orderLevelDiscountCode|string|Order Level Discount code applied at the item level of a transaction. |FRIENDSANDFAMILY20, EASTER10|||||||
|transaction.payment[n].loyaltyPointsAmount|integer|Number of loyalty points |100, 101, 1000||||0|||
|transaction.payment[n].paymentAmount|string|String representation of the payment amount. Positive. Up to two decimal places for cents. No currency symbol.|200, 29.99, 50, 0|^[0-9]*(\.[0-9]{1,2})?$||||||
|transaction.payment[n].paymentGateway|string|Captures the digital payment gateway was used to complete transactions for orders?|PayPal, Stripe|||||||
|transaction.payment[n].paymentID|string|Unique identifier of a payment.  Typically an integration key from a back-end system.|ZPH-87698-098|||||||
|transaction.payment[n].paymentMethod|string|Describes the method of payment for a transaction. |Credit Card, PayPal, Mastercard, Visa, Amex, Discover|||||||
|transaction.profile.address.country|string|Indicates the country of the billing address. ISO 3166 \(alpha-2\) Uppercase.|US, CA, FR, UK|^[A-Z]{2}$||||||
|transaction.profile.address.postalCode|string|The mailing zip or postal code associated with the billing address. |53533, 30381, M1R 0E9, M3C 0C1|||||||
|transaction.purchaseID|string|Unique identifier of the purchase. Max Length 20. Used as Unique ID of the purchase or deduplication.|ABC-132456789, DEF-132456789, 0987654567|^[a-zA-Z0-9]{6,20}$|6|20||||
|transaction.total.currency|string|Currency of the transaction. ISO 4217 \(3 character alpha\), uppercase |USD, CAD, GBP, CHF|^[A-Z]{3}$|3|3||||
|transaction.total.numPayments|integer|Collects the number of payment methods used for an order at order confirmaton||||||||
|transaction.total.revenue|string|The total revenue for a transaction. Does not include tax or shipping. |125.05, 432.21, 90.22, 12.05|^[0-9]*(\.[0-9]{1,2})?$||||||





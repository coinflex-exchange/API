# CoinFLEX BIST API

- [What Is the BIST API](#what-is-the-bist-api)
- [Request Limits](#request-limits)
- [Public Data Functions](#public-data-functions)
  - [Ticker](#ticker)
  - [Order Book](#order-book)
- [API Authentication](#api-authentication)
- [Private Functions](#private-functions)
  - [Account Balance](#account-balance)
  - [User Transactions](#user-transactions)
  - [Open Orders](#open-orders)
  - [Cancel Order](#cancel-order)
  - [Buy Limit Order](#buy-limit-order)
  - [Sell Limit Order](#sell-limit-order)
  - [Buy Market Order](#buy-market-order)
  - [Sell Market Order](#sell-market-order)
  - [Estimate Buy Market Order](#estimate-buy-market-order)
  - [Estimate Sell Market Order](#estimate-sell-market-order)

## WHAT IS THE BIST API?

CoinFLEX offers an API gateway called <u>BIST</u> that approximately emulates [Bitstamp's v1 HTTP API](https://www.bitstamp.net/api/). This following document is provided as a quick reference to this API. For complete details, please consult the documentation of Bitstamp's v1 HTTP API and our document detailing [the differences between Bitstamp's v1 HTTP API and BIST](https://github.com/coinflex-exchange/API/blob/master/BIST-Migration.md).

Bitstamp was not a multi-currency exchange at the time this emulation layer was implemented. Because CoinFLEX is a multi-currency exchange, CoinFLEX emulates the entire Bitstamp v1 API at multiple separate endpoints, one for each market that CoinFLEX operates.

The Bitstamp-like API can be accessed at the following API endpoints:

DEMO site

* `https://demowebapi.coinflex.com/bist/<base>/<counter>/`

LIVE site

* `https://webapi.coinflex.com/bist/<base>/<counter>/`     (go-live settings - currently turned off)

`<base>` and `<counter>` are placeholders for asset codes listed in the "Asset Type" column of [SCALE.md](SCALE.md).

These endpoint URIs replace the `https://www.bitstamp.net/api/` portion of Bitstamp's URIs.

**N.B: All examples below use the XBT/USDT asset pair on the CoinFLEX platform, but this can be changed to the asset pair and platform of your choice.**


## REQUEST LIMITS

CoinFLEX's application programming interface (API) allows our clients to access and control their accounts or view our market data using custom-written software. To protect the performance of the system, we impose certain limits. See [LIMITS.md](LIMITS.md) for details.


## PUBLIC DATA FUNCTIONS

#### TICKER
DEMO site

GET https://demowebapi.coinflex.com/bist/XBT/USDT/ticker/

LIVE site

GET https://webapi.coinflex.com/bist/XBT/USDT/ticker/      (go-live settings - currently turned off)

Returns JSON dictionary:

* last - last BTC price
* high - last 24 hours price high
* low - last 24 hours price low
* vwap - last 24 hours volume weighted average price: [vwap](http://en.wikipedia.org/wiki/Volume-weighted_average_price)
* volume - last 24 hours volume
* bid - highest buy order
* ask - lowest sell order

**N.B:**

1. Please refer to the Date HTTP response header for any date or time information you may require.

2. CoinFLEX returns null for any ticker fields that are not populated, as may happen if no trade has occurred in the past 24 hours.

#### ORDER BOOK
DEMO site

GET https://demowebapi.coinflex.com/bist/XBT/USDT/order_book/

LIVE site

GET https://webapi.coinflex.com/bist/XBT/USDT/order_book/  (go-live settings - currently turned off)

Returns JSON dictionary with "bids" and "asks". Each is a list of open orders and each order is represented as a list of price and amount.

**N.B:**


1. Please refer to the Date HTTP response header for any date or time information you may require.


## API AUTHENTICATION
All private API calls require authentication. You need to provide 3 parameters to authenticate a request:

* User ID
* API key
* Passphrase

#### User ID
To get your User ID (sometimes referred to as a Core ID), go to the Dashboard

#### API key
To get your API key (referred to as a "Cookie" in the WebSocket API documentation), go to the Dashboard

#### Passphrase
Is the password you use to log into CoinFLEX.

**N.B:**

1. CoinFLEX authenticates requests using standard HTTP Basic authentication. The username portion of the Basic credentials is constructed by concatenating the numeric user ID, a slash, and the user's API authentication cookie. The password portion is simply the user's login passphrase.

2. Many off-the-shelf HTTP clients (including cURL and all web browsers) can generate the HTTP Basic Authorization request header.

This is an example of how to make a balance request with curl:

DEMO site

> ``curl -k -u '[User ID]/[API key]:[Passphrase]' https://demowebapi.coinflex.com/bist/XBT/USDT/balance/``

LIVE site

> ``curl -k -u '[User ID]/[API key]:[Passphrase]' https://webapi.coinflex.com/bist/XBT/USDT/balance/``  (go-live settings - currently turned off)

* ``User ID`` and ``API key`` are provided on your CoinFLEX logged in Dashboard page.
* ``Passphrase`` is your CoinFLEX passphrase.

## PRIVATE FUNCTIONS

#### ACCOUNT BALANCE
Demo site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/balance/

Demo site

POST https://webapi.coinflex.com/bist/XBT/USDT/balance/  (go-live settings - currently turned off)

Params:

* User ID - user ID
* API key - api key
* Passphrase - passphrase


Returns JSON dictionary:

* usdt_balance - USDT balance
* usdc_balance - USDC balance
* xbt_balance - XBT balance
* xbt_reserved - XBT reserved in open orders
* usdt_reserved - USDT reserved in open orders
* usdc_reserved - USDC reserved in open orders
* usdt_available- USDT available for trading
* usdc_available- USDC available for trading
* xbt_available - XBT available for trading

**N.B:**

1. Bitstamp returns fields whose names are constructed by appending _balance, _reserved, or _available to a currency code, which is either btc or usd. CoinFLEX constructs these field names using currency codes xbt, usdt, and/or usdc, depending on the specific API endpoint being accessed.

2. CoinFLEX does not include the fee field in the response.


#### USER TRANSACTIONS
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/user_transactions/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/user_transactions/   (go-live settings - currently turned off)

Params:

* User ID - user ID
* API key - api key
* Passphrase - passphrase
* offset - skip that many transactions before beginning to return results. Default: 0.
* limit - limit result to that many transactions. Default: 100. Maximum: 1000.
* sort - sorting by date and time (asc - ascending; desc - descending). Default: desc.

Returns descending JSON list of transactions. Every transaction (dictionary) contains:

* datetime - date and time
* id - transaction id
* type - transaction type (0 - deposit; 1 - withdrawal; 2 - market trade)
* usdt - USDT amount
* usdc - USDC amount
* xbt - XBT amount
* xbt_usdt - XBT/USDT price
* usdt_usdc - USDT/USDC price
* fee - transaction fee
* order_id - executed order id

**N.B:**

1. Bitstamp returns the quantity and total of each trade in the btc and usd fields, respectively, and returns the trade price in the (undocumented) btc_usd field. CoinFLEX names these fields using currency codes xbt, usdt, and/or usdc, depending on the specific API endpoint being accessed.

#### OPEN ORDERS
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/open_orders/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/open_orders/  (go-live settings - currently turned off)

Params:

* User ID - user ID
* API key - api key
* Passphrase - passphrase

Returns JSON list of open orders. Each order is represented as dictionary:

* id - order id
* datetime - date and time
* type - buy or sell (0 - buy; 1 - sell)
* price - price
* amount - amount

#### CANCEL ORDER
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/cancel_order/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/cancel_order/ (go-live settings - currently turned off)

Params:

* User ID - user ID
* API key - api key
* Passphrase - passphrase
* id - order ID

Returns 'true' if order has been found and canceled.

**N.B:**

1. If the specified order could not be found, CoinFLEX returns **false**.

2. If the specified order was found and canceled, CoinFLEX returns **true** with a Content-Type: text/plain header in this case.

#### BUY LIMIT ORDER
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/buy/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/buy/  (go-live site - currently turned off)

Params:

* User ID - user ID
* API key - api key
* Passphrase - passphrase
* amount - amount
* price - price
* nonce - optional nonce parameter.  If given, it must be positive
* ttl - optional parameter that specifies a time-to-live for the order in seconds. If given, it must be positive and must not exceed 86400 (24 hours)

Returns JSON dictionary representing order:

* id - order id
* datetime - date and time
* type - buy or sell (0 - buy; 1 - sell)
* price - price
* amount - amount

**N.B:**

1. CoinFLEX supports the use of tonces via the optional **nonce** request parameter. When used, each order placed must specify a tonce that is greater than that specified on any previous order since the nonce counter was last reset.  The nonce counter can only be reset via the WebSocket API. 

2. CoinFLEX supports an optional time-to-live parameter on orders. If given, the placed order will be canceled automatically after the specified time if it has not already been closed otherwise. It must be positive and must not exceed 86400 (24 hours).

    a. Note that extenuating circumstances (such as heavy traffic or system upgrades) may force orders placed with times-to-live to be canceled sooner than specified. (This proviso does not apply to orders placed without a time-to-live.)

3. CoinFLEX returns a datetime field with whole-second precision.

#### SELL LIMIT ORDER
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/sell/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/sell/  (go-live settings - currently turned off)

Params:

* User ID - user ID
* API key - api key
* Passphrase - passphrase
* amount - amount
* price - price
* nonce - optional nonce parameter.  If given, it must be positive
* ttl - optional parameter that specifies a time-to-live for the order in seconds. If given, it must be positive and must not exceed 86400 (24 hours)

Returns JSON dictionary representing order:

* id - order id
* datetime - date and time
* type - buy or sell (0 - buy; 1 - sell)
* price - price
* amount - amount

**N.B:**

1. CoinFLEX supports the use of tonces via the optional **nonce** request parameter. When used, each order placed must specify a tonce that is greater than that specified on any previous order since the nonce counter was last reset.  The nonce counter can only be reset via the WebSocket API. 

2. CoinFLEX supports an optional time-to-live parameter on orders. If given, the placed order will be canceled automatically after the specified time if it has not already been closed otherwise. It must be positive and must not exceed 86400 (24 hours).

    a. Note that extenuating circumstances (such as heavy traffic or system upgrades) may force orders placed with times-to-live to be canceled sooner than specified. (This proviso does not apply to orders placed without a time-to-live.)

3. CoinFLEX returns a datetime field with whole-second precision.

#### BUY MARKET ORDER
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/buy_market/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/buy_market/  (go-live settings - currently turned off)

Params:

* quantity - an amount of the base asset to buy OR
* total - an amount of the counter asset with which to buy the base asset

Returns JSON dictionary representing order:

* remaining - how much of the requested quantity or total could not be traded

#### SELL MARKET ORDER 
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/sell_market/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/sell_market/ (go-live settings - currently turned off)

Params:

* quantity - an amount of the base asset to sell OR
* total - an amount of the counter asset for which to sell the base asset

Returns JSON dictionary representing order:

* remaining - how much of the requested quantity or total could not be traded


#### ESTIMATE BUY MARKET ORDER
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/estimate_buy_market/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/estimate_buy_market/ (go-live site - currently turned off)

Params:

* quantity - an amount of the base asset that would be bought OR
* total - an amount of the counter asset with which the base asset would be bought

Returns JSON dictionary representing estimate:

* quantity - amount of the base asset that would have been traded
* total - amount of the counter asset that would have been traded


#### ESTIMATE SELL MARKET ORDER
DEMO site

POST https://demowebapi.coinflex.com/bist/XBT/USDT/estimate_sell_market/

LIVE site

POST https://webapi.coinflex.com/bist/XBT/USDT/estimate_sell_market/  (go-live site - currently turned off)

Params:

* quantity - an amount of the base asset that would be sold OR
* total - an amount of the counter asset for which the base asset would be sold

Returns JSON dictionary representing estimate:

* quantity - amount of the base asset that would have been traded
* total - amount of the counter asset that would have been traded

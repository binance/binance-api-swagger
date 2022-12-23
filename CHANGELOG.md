# Changelog

## 1.14.0 - 2022-12-23
### Added
VIP Loans:
- `GET /sapi/v1/loan/vip/collateral/account`: Check Locked Value of VIP Collateral Account
- `GET /sapi/v1/loan/vip/ongoing/orders`: Get VIP Loan Ongoing Orders
- `POST /sapi/v1/loan/vip/repay`: VIP Loan Repay
- `GET /sapi/v1/loan/vip/repay/history`: Get VIP Loan Repayment History

Crypto Loan:
- `GET /sapi/v1/loan/loanable/data`: Get interest rate and borrow limit of loanable assets. The borrow limit is shown in USD value.
- `GET /sapi/v1/loan/collateral/data`: Get LTV information and collateral limit of collateral assets. The collateral limit is shown in USD value.
- `GET /sapi/v1/loan/repay/collateral/rate`: Get the the rate of collateral coin / loan coin when using collateral repay, the rate will be valid within 8 second.
- `POST /sapi/v1/loan/customize/margin_call`: Customize margin call for ongoing orders only.

Convert:
- `GET /sapi/v1/convert/exchangeInfo`: Query for all convertible token pairs and the tokens’ respective upper/lower limits
- `GET /sapi/v1/convert/assetInfo`: Query for supported asset’s precision information
- `POST /sapi/v1/convert/getQuote`: Request a quote for the requested token pairs
- `POST /sapi/v1/convert/acceptQuote`: Accept the offered quote by quote ID.
- `GET /sapi/v1/convert/orderStatus`: Query order status by order ID.

Wallet:
- `GET /sapi/v1/asset/ledger-transfer/cloud-mining/queryByPage`: The query of Cloud-Mining payment and refund history

Sub-account:
- `GET /sapi/v1/sub-account/apiRestrictions/ipRestriction/thirdPartyList`: To query Sub-Account API key Third Party IP whitelist
- `POST /sapi/v2/sub-account/subAccountApi/ipRestriction`: To support master account update IP Restriction for Sub-Account API key

Binance Code:
- `POST /sapi/v1/giftcard/buyCode`: For buying a fixed-value Binance Code.
- `GET /sapi/v1/giftcard/buyCode/token-limit`: To verify which tokens are available for you to purchase fixed-value gift cards as mentioned in section 2 and its’ limitation.

## 1.13.1 - 2022-11-23
### Changed
- Upgrade Swagger UI


## 1.13.0 - 2022-10-13

### Added
- New endpoints for Futures:
  - `POST /sapi/v1/futures/transfer`
  - `GET /sapi/v1/futures/transfer`
  - `GET /sapi/v1/futures/loan/borrow/history`
  - `GET /sapi/v1/futures/loan/repay/history`
  - `GET /sapi/v2/futures/loan/wallet`
  - `GET /sapi/v1/futures/loan/adjustCollateral/history`
  - `GET /sapi/v1/futures/loan/liquidationHistory`
  - `GET /sapi/v1/futures/loan/interestHistory`
- New endpoints for Futures Algo:
  - `POST /sapi/v1/algo/futures/newOrderVp`
  - `POST /sapi/v1/algo/futures/newOrderTwap`
  - `DELETE /sapi/v1/algo/futures/order`
  - `GET /sapi/v1/algo/futures/openOrders`
  - `GET /sapi/v1/algo/futures/historicalOrders`
  - `GET /sapi/v1/algo/futures/subOrders`
- New endpoint for Margin：
  - `GET /sapi/v1/margin/tradeCoeff`: Get personal margin level information
- New endpoints for Wallet:
  - `POST /sapi/v1/asset/convert-transfer`: Convert transfer, convert between BUSD and stablecoins.
  - `POST /sapi/v1/asset/convert-transfer/queryByPage`: Query convert transfer
- New endpoints for Crypto Loan
  - `POST /sapi/v1/loan/borrow`: Borrow - Crypto Loan Borrow
  - `GET /sapi/v1/loan/borrow/history`: Borrow - Get Loan Borrow History
  - `GET /sapi/v1/loan/ongoing/orders`: Borrow - Get Loan Ongoing Orders
  - `POST /sapi/v1/loan/repay`: Repay - Crypto Loan Repay
  - `GET /sapi/v1/loan/repay/history`: Repay - Get Loan Repayment History
  - `POST /sapi/v1/loan/adjust/ltv`: Adjust LTV - Crypto Loan Adjust LTV
  - `GET /sapi/v1/loan/ltv/adjustment/history`: Adjust LTV - Get Loan LTV Adjustment History

### Changed
- Changes to `GET /api/v3/exchangeInfo`
  - New optional parameter permissions added to display all symbols with the permissions matching the parameter provided. (eg.SPOT, MARGIN, LEVERAGED)
  - If not provided, the default value will be ["SPOT","MARGIN", "LEVERAGED"].
- Update endpoint for Sub-Account:
  - `POST /sapi/v1/sub-account/subAccountApi/ipRestriction`: Add new param thirdParty
  - `POST /sapi/v1/sub-account/subAccountApi/ipRestriction/ipList`: Add new param thirdPartyName
  - `DELETE /sapi/v1/sub-account/subAccountApi/ipRestriction/ipList`: Add new param thirdPartyName

## 1.12.0 - 2022-08-29

### Added
- New endpoint for Market:
  - `GET /api/v3/uiKlines`

- New kline interval: `1s`

- New field `brokered` has been added to `GET /api/v3/account`

### Changed
- Changes to `GET /api/v3/ticker` and `GET /api/v3/ticker/24hr`
  - New optional parameter type added
  - Supported values for parameter type are FULL and MINI
    - FULL is the default value and the response that is currently being returned from the endpoint
    - MINI omits the following fields from the response: priceChangePercent, weightedAvgPrice, bidPrice, bidQty, askPrice, askQty, and lastQty

## 1.11.0 - 2022-08-15

### Added
New endpoint for Portfolio Margin:
- `GET /sapi/v1/portfolio/pmLoan` to query Portfolio Margin Bankruptcy Loan Record.
- `POST /sapi/v1/portfolio/repay` to repay Portfolio Margin Bankruptcy Loan.
- `GET /sapi/v1/portfolio/collateralRate` to get Portfolio Margin Collateral Rate.

### Changed
Changed endpoints for Trade:
  - `POST /api/v3/order/test` New optional fields `strategyId` and `strategyType`.
  - `POST /api/v3/order` New optional fields `strategyId` and `strategyType`.
  - `POST /api/v3/order/cancelReplace` New optional fields `strategyId` and `strategyType`.
  - `POST /api/v3/order/oco` New optional fields `limitStrategyId`, `limitStrategyType`, `stopStrategyId` and `stopStrategyType`.

## 1.10.0 - 2022-07-19

### Added
- New endpoint for Market:
  - `GET /api/v3/ticker` for rolling window price change statistics based on windowSize provided.

- New endpoints for Trade:
  - `POST /api/v3/order/cancelReplace` to cancel an existing order and place a new order on the same symbol.

- New endpoint for Margin:
  - `POST /sapi/v3/asset/getUserAsset` to get user assets.

- New endpoint for Wallet:
  - `GET /sapi/v1/margin/dribblet` to query the historical information of user's margin account small-value asset conversion BNB.

### Changed
- Update endpoint for Fiat:
  - `GET /sapi/v1/fiat/orders`: Weight changes from IP(1) to UID(90000)

- Update endpoint for Pay:
  - `GET /sapi/v1/pay/transactions`: Param names changed: startTimestamp -> startTime; endTimestamp -> endTime.

- Update endpoint for Convert:
  - `GET /sapi/v1/fiat/orders`: Weight changes from IP(3000) to IP(100)

## 1.9.0 - 2022-05-23

### Added
- New endpoint for Gift Card:
  - `GET /sapi/v1/giftcard/cryptography/rsa-public-key` to fetch RSA public key.

- New endpoints for Staking:
  - `GET /sapi/v1/staking/productList` to get Staking product list
  - `POST /sapi/v1/staking/purchase` to stake product
  - `POST /sapi/v1/staking/redeem` to redeem product
  -   `GET /sapi/v1/staking/position` to get Staking product holding position
  - `GET /sapi/v1/staking/stakingRecord` to inquiry Staking history records
  - `POST /sapi/v1/staking/setAutoStaking` to set Auto Staking function
  - `GET /sapi/v1/staking/personalLeftQuota` to inquiry Staking left quota

- New endpoint for Portfolio Margin:
  - `GET /sapi/v1/portfolio/account` to support query portfolio margin account info.

- New endpoint for Margin:
  - `GET /sapi/v1/margin/rateLimit/order` to display the user's current margin order count usage for all intervals.

### Changed
- Update endpoint for Binance Code:
  - `POST /sapi/v1/giftcard/redeemCode`: new optional parameter externalUid. Each external unique ID represents a unique user on the partner platform. The function helps you to identify the redemption behavior of different users.

- Update endpoints for Market:
  - `GET /api/v3/ticker/24hr`, `GET /api/v3/ticker/price` and `GET /api/v3/ticker/bookTicker` new optional parameter symbols.

## 1.8.0 - 2022-04-22

### Added
- New transfer types `MARGIN`, `ISOLATED_MARGIN` and parameter `symbol` to `POST /sapi/v1/sub-account/universalTransfer`
- New endpoint `GET /sapi/v1/managed-subaccount/accountSnapshot` to support investor master account query asset snapshot of managed sub-account.
- New optional parameter `trailingDelta` to `POST /api/v3/order`, `POST /api/v3/order/test` and `POST /api/v3/order/oco`

### Changed
- `GET /sapi/v1/sub-account/universalTransfer` The query time period must be less then 30 days; If startTime and endTime not sent, return records of the last 30 days by default.
- `/sapi/v1/capital/withdraw/history` Response fields confirmNo and info are now optional.

## 1.7.0 - 2022-03-04

### Added
- Parameter `type` to `POST /sapi/v1/bswap/liquidityAdd`
- Response field `allowTrailingStop` to ` GET /api/v3/exchangeInfo`
- Response fields `isManagedSubAccount` and `isAssetManagementSubAccount` to `GET /sapi/v1/sub-account/list`

### Changed
- Corrected multiple parameters from different endpoints to be in sync with the API Doc
- Updated parameter `limit` from `GET api/v3/depth` to englobe its new functionality

## 1.6.0 - 2022-02-17

### Added
- New endpoints for Binance Gift Card:
    - `POST /sapi/v1/giftcard/createCode` to create a Binance Code.
    - `POST /sapi/v1/giftcard/redeemCode` to redeem a Binance Code.
    - `GET /sapi/v1/giftcard/verify` to verify a Binance Code.
- New endpoint `POST /sapi/v1/asset/dust-btc` to get assets that can be converted into BNB.

### Changed
- Added missing field `network` to `/sapi/v1/capital/config/getall` 200 response
- Correct from `POST /sapi/v1/bswap/unclaimedRewards` to `POST /sapi/v1/bswap/claimRewards`
- Correct `GET /sapi/v1/asset/assetDividend` parameter `limit`
- Correct `POST /sapi/v1/asset/dust` parameter `asset`
- Update description of ENUM parameters to follow same format for values explanation
- Update query limits of `GET /sapi/v1/accountSnapshot`

## 1.5.0 - 2022-01-07

### Added
- New parameter `clientTranId` added in `POST /sapi/v1/sub-account/universalTransfer` and `GET /sapi/v1/sub-account/universalTransfer` to support custom transfer id
- New endpoint `GET /sapi/v1/mining/payment/uid` to get Mining account earning.
- New endpoint `GET /sapi/v1/bswap/unclaimedRewards` to get unclaimed rewards record.
- New endpoint `POST /sapi/v1/bswap/claimRewards` to claim swap rewards or liquidity rewards.
- New endpoint `GET /sapi/v1/bswap/claimedHistory`to get history of claimed rewards.

### Changed
- Corrected some `limit` parameters' type from `string` to `integer`

### Removed
- Parameter `limit` from `GET /sapi/v1/margin/interestRateHistory`
- Transfer types `MAIN_MINING`, `MINING_MAIN`, `MINING_UMFUTURE`, `MARGIN_MINING`, and `MINING_MARGIN` as they are discontinued in Universal Transfer endpoint `POST /sapi/v1/asset/transfer` from January 05, 2022 08:00 AM UTC

## 1.4.0 - 2021-12-14

### Added
- New endpoint `GET /sapi/v1/convert/tradeFlow` to support user query convert trade history records
- New endpoint `GET /sapi/v1/rebate/taxQuery` to support user query spot rebate history records
- New endpoints for NFT:
    - `GET /sapi/v1/nft/history/transactions` to get NFT transaction history
    - `GET /sapi/v1/nft/history/deposit` to get NFT deposit history
    - `GET /sapi/v1/nft/history/withdraw` to get NFT withdraw history
    - `GET /sapi/v1/nft/user/getAsset` to get NFT asset
- New endpoints for Margin:
    - `GET /sapi/v1/margin/crossMarginData` to get cross margin fee data collection
    - `GET /sapi/v1/margin/isolatedMarginData` to get isolated margin fee data collection
    - `GET /sapi/v1/margin/isolatedMarginTier` to get isolated margin tier data collection

## 1.3.0 - 2021-11-24

### Added
- New endpoint `GET /sapi/v1/loan/income` to query crypto loan history
- New endpoint `GET /sapi/v1/pay/transactions` to support user query Pay trade history
- New endpoints for Sub-Account:
    - `POST /sapi/v1/sub-account/subAccountApi/ipRestriction` to support master account enable and disable IP restriction for a sub-account API Key
    - `POST /sapi/v1/sub-account/subAccountApi/ipRestriction/ipList` to support master account add IP list for a sub-account API Key
    - `GET /sapi/v1/sub-account/subAccountApi/ipRestriction` to support master account query IP restriction for a sub-account API Key
    - `DELETE /sapi/v1/sub-account/subAccountApi/ipRestriction/ipList` to support master account delete IP list for a sub-account API Key

### Changed
- New response field `info` added in `GET /sapi/v1/capital/withdraw/history` to show the reason for withdrawal failure

## 1.2.0 - 2021-11-05

### Added
- New endpoint `GET api/v3/rateLimit/order` to display the user's current order count usage for all intervals
- New parameter `walletType` in `POST /sapi/v1/capital/withdraw/apply` to choose which wallet to withdraw

## 1.1.0 - 2021-10-25

### Added
- New endpoints for BSwap:
    - `GET /sapi/v1/bswap/poolConfigure` to get pool configure
    - `GET /sapi/v1/bswap/addLiquidityPreview` to calculate expected share amount for adding liquidity in single or dual token
    - `GET /sapi/v1/bswap/removeLiquidityPreview` to calculate expected asset amount of single token redemption or dual token redemption

- Additional properties to specify `array` type: `minItems` and `maxItems`
- Additional format properties to specify `integer` type: `int32` and `int64`
- Additional format properties to specify `number` type: `float` and `double`
- Additional property `required` for response fields

## 1.0.0 - 2021-09-11

### Added
- First release

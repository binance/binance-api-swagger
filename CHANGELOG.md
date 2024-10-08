# Changelog

## 1.22.0 - 2024-10-08
### Added
**Trade**
- `POST /api/v3/orderList/oto`
- `POST /api/v3/orderList/otoco`

**Margin Trading**
- `POST /sapi/v1/margin/order/oto`
- `POST /sapi/v1/margin/order/otoco`

**Simple Earn**
- `POST /sapi/v1/simple-earn/locked/setRedeemOption`

**Copy Trading**
- `GET /sapi/v1/copyTrading/futures/userStatus`
- `GET /sapi/v1/copyTrading/futures/leadSymbol`

**Portfolio Margin**
- `GET /sapi/v2/portfolio/collateralRate`

### Updated
**Trade**
- `POST /api/v3/order/oco` is deprecated. Update to the new `POST /api/v3/orderList/oco` endpoint.

**Margin Trading**
- New parameters added into response body to replace the parameter of 'transferEnabled' in the endpoint of `GET /sapi/v1/margin/account`: `created`, `collateralMarginLevel`, `TotalCollateralValueInUSDT`, `transferInEnabled`, `transferOutEnabled`, `accountType`

**Simple Earn**
- `POST /sapi/v1/simple-earn/locked/subscribe` new parameter: `redeemTo`
- `GET /sapi/v1/simple-earn/locked/position` new fields in response: `redeemTo`, `parentPositionId`, `rewardAmt`, `extraRewardAsset`, `extraRewardAPR`, `estExtraRewardAmt`, `nextPay`, `nextPayDate`, `payPeriod`, `redeemAmountEarly`, `rewardsEndDate`, `deliverDate`, `redeemPeriod`, `redeemingAmt`, `redeemTo`, `partialAmtDeliverDate`, `canRedeemEarly`, `canFastRedemption`, `autoSubscribe`, `type`, `status`, `canReStake`
- `GET /sapi/v1/simple-earn/flexible/history/subscriptionRecord` new fields in response: `productId`
- `GET /sapi/v1/simple-earn/locked/history/subscriptionRecord` new fields in response: `projectId`
- `GET /sapi/v1/simple-earn/locked/history/redemptionRecord` new fields in response: `originalAmount`, `lossAmount`, `isComplete`, `rewardAsset`, `rewardAmt`, `extraRewardAsset`, `estExtraRewardAm`

## 1.21.0 - 2024-06-06
### Added
- `GET /api/v3/account/commission`
- `GET /api/v3/ticker/tradingDay`

**Convert**
- `POST /sapi/v1/convert/limit/placeOrder`
- `POST /sapi/v1/convert/limit/cancelOrder`
- `GET /sapi/v1/convert/limit/queryOpenOrders`

**Dual Investment**
- `GET /sapi/v1/dci/product/list`
- `POST /sapi/v1/dci/product/subscribe`
- `GET /sapi/v1/dci/product/positions`
- `GET /sapi/v1/dci/product/accounts`
- `POST /sapi/v1/dci/product/auto_compound/edit-status`

**Margin**
- `POST /sapi/v1/margin/borrow-repay`
- `GET /sapi/v1/margin/borrow-repay`
- `GET /sapi/v1/spot/delist-schedule`

**Staking**
- `POST /sapi/v2/eth-staking/eth/stake`
- `POST /sapi/v1/eth-staking/eth/redeem`
- `GET /sapi/v1/eth-staking/eth/history/stakingHistory`
- `GET /sapi/v1/eth-staking/eth/history/redemptionHistory`
- `GET /sapi/v1/eth-staking/eth/history/rewardsHistory`
- `GET /sapi/v1/eth-staking/eth/quota`
- `GET /sapi/v1/eth-staking/eth/history/rateHistory`
- `GET /sapi/v2/eth-staking/account`
- `POST /sapi/v1/eth-staking/wbeth/wrap`
- `GET /sapi/v1/eth-staking/wbeth/history/wrapHistory`
- `GET /sapi/v1/eth-staking/wbeth/history/unwrapHistory`
- `GET /sapi/v1/eth-staking/eth/history/wbethRewardsHistory`

**Wallet**
- `GET /sapi/v1/capital/withdraw/address/list`
- `GET /sapi/v1/account/info`

### Changed
**Gift Card**
- `POST /sapi/v1/giftcard/createCode`: add response field `expiredTime`
- `POST /sapi/v1/giftcard/buyCode`: add response field `expiredTime`

**Loan**
- Updated `POST /sapi/v1/loan/flexible/borrow` to `POST /sapi/v2/loan/flexible/borrow`
- Updated `GET /sapi/v1/loan/flexible/loanable/data` to `GET /sapi/v2/loan/flexible/loanable/data`
- Updated `GET /sapi/v1/loan/flexible/collateral/data` to `GET /sapi/v2/loan/flexible/collateral/data`
- Updated `GET /sapi/v1/loan/flexible/ongoing/orders` to `GET /sapi/v2/loan/flexible/ongoing/orders`
- Updated `POST /sapi/v1/loan/flexible/repay` to `POST /sapi/v2/loan/flexible/repay`
- Updated `POST /sapi/v1/loan/flexible/adjust/ltv` to `POST /sapi/v2/loan/flexible/adjust/ltv`
- Updated `GET /sapi/v1/loan/flexible/borrow/history` to `GET /sapi/v2/loan/flexible/borrow/history`
- Updated `GET /sapi/v1/loan/flexible/repay/history` to `GET /sapi/v2/loan/flexible/repay/history`
- Updated `GET /sapi/v1/loan/flexible/ltv/adjustment/history` to `GET /sapi/v2/loan/flexible/ltv/adjustment/history`

**Market**
- `GET /api/v3/avgPrice`: response has a new field `closeTime`
- `GET /api/v3/klines` and `GET /api/v3/uiKlines` have a new optional parameter `timeZone`
- `GET /api/v3/exchangeInfo`: add `otoAllowed`, `cancelReplaceAllowed` and `permissionSets` in response

**Margin**
- `GET /sapi/v1/margin/transfer`: add parameter `isolatedSymbol`
- `GET /sapi/v1/margin/allAssets`: add parameter `asset`
- `GET /sapi/v1/margin/allPairs`: add parameter `symbol`
- `GET /sapi/v1/margin/isolated/allPairs`: add parameter `symbol`

**Trade**
- `POST /api/v3/order/test` and POST `/api/v3/sor/order/test` have a new optional parameter `computeCommissionRates`

**Wallet**
- `GET /sapi/v1/asset/dribblet`: add parameter `accountType`
- `POST /sapi/v1/asset/dust-btc`: add parameter `accountType`
- `POST /sapi/v1/asset/dust`: add parameter `accountType`
- `GET /sapi/v1/capital/config/getall`: remove response field `resetAddressStatus`

### Deleted
**Bswap**
- `GET /sapi/v1/bswap/pools`
- `GET /sapi/v1/bswap/liquidity`
- `POST /sapi/v1/bswap/liquidityAdd`
- `POST /sapi/v1/bswap/liquidityRemove`
- `GET /sapi/v1/bswap/liquidityOps`
- `GET /sapi/v1/bswap/quote`
- `POST /sapi/v1/bswap/swap`
- `GET /sapi/v1/bswap/swap`
- `GET /sapi/v1/bswap/poolConfigure`
- `GET /sapi/v1/bswap/addLiquidityPreview`
- `GET /sapi/v1/bswap/removeLiquidityPreview`
- `GET /sapi/v1/bswap/unclaimedRewards`
- `POST /sapi/v1/bswap/claimRewards`
- `GET /sapi/v1/bswap/claimedHistory`

**Margin**
- `POST /sapi/v1/margin/transfer`
- `POST /sapi/v1/margin/isolated/transfer`
- `POST /sapi/v1/margin/loan`
- `POST /sapi/v1/margin/repay`
- `GET /sapi/v1/margin/isolated/transfer`
- `GET /sapi/v1/margin/asset`
- `GET /sapi/v1/margin/pair`
- `GET /sapi/v1/margin/isolated/pair`
- `GET /sapi/v1/margin/loan`
- `GET /sapi/v1/margin/repay`
- `GET /sapi/v1/margin/dribblet`
- `GET /sapi/v1/margin/dust`
- `POST /sapi/v1/margin/dust`

**Staking**
- `GET /sapi/v1/staking/productList`
- `POST /sapi/v1/staking/purchase`
- `POST /sapi/v1/staking/redeem`
- `GET /sapi/v1/staking/position`
- `GET /sapi/v1/staking/stakingRecord`
- `POST /sapi/v1/staking/setAutoStaking`
- `GET /sapi/v1/staking/personalLeftQuota`

## 1.20.1 - 2023-12-07
- Minor updates

## 1.20.0 - 2023-11-23
### Added
- `GET /sapi/v1/capital/deposit/address/list`
- `GET /sapi/v1/margin/leverageBracket`

## 1.19.0 - 2023-11-15
### Added
- `GET /sapi/v1/loan/vip/request/interestRate`
- `GET /sapi/v1/margin/capital-flow`
- `GET /sapi/v1/margin/delist-schedule`
- `GET /sapi/v1/margin/available-inventory`
- `POST /sapi/v1/margin/manual-liquidation`
- `GET /sapi/v1/portfolio/margin-asset-leverage`
- `GET /sapi/v1/loan/vip/collateral/data`
- `GET /api/v3/myAllocations`
- `POST /api/v3/sor/order`
- `POST /api/v3/sor/order/test`

### Changed
- `GET /api/v3/trades`
- `GET /api/v3/depth`
- `GET /sapi/v1/account/apiRestrictions`
- `GET /sapi/v1/loan/vip/request/data`
- `POST /api/v3/userDataStream`
- `PUT /api/v3/userDataStream`
- `DELETE /api/v3/userDataStream`
- `GET /sapi/v1/capital/withdraw/history`
- `POST /sapi/v1/margin/max-leverage`
- `GET /api/v3/openOrderList`
- `GET /api/v3/rateLimit/order`
- `GET /api/v3/myTrades`
- `GET /api/v3/account`
- `GET /api/v3/allOrderList`
- `GET /api/v3/orderList`
- `GET /api/v3/openOrders`
- `GET /api/v3/order`
- `GET /api/v3/ticker`
- `GET /api/v3/ticker/bookTicker`
- `GET /api/v3/ticker/price`
- `GET /api/v3/ticker/24hr`
- `GET /api/v3/avgPrice`
- `GET /api/v3/uiKlines`
- `GET /api/v3/klines`
- `GET /api/v3/aggTrades`
- `GET /api/v3/historicalTrades`
- `GET /api/v3/allOrders`


## 1.18.0 - 2023-09-27
### Added
- `GET /sapi/v1/lending/auto-invest/index/info`
- `GET /sapi/v1/lending/auto-invest/index/user-summary`
- `POST /sapi/v1/lending/auto-invest/one-off`
- `GET /sapi/v1/lending/auto-invest/one-off/status`
- `POST /sapi/v1/lending/auto-invest/redeem`
- `GET /sapi/v1/lending/auto-invest/redeem/history`
- `GET /sapi/v1/lending/auto-invest/rebalance/history`
- `GET /sapi/v1/asset/wallet/balance`
- `GET /sapi/v1/asset/custody/transfer-history`
- `GET /sapi/v1/futures/histDataLink`

### Changed
- `GET /sapi/v1/margin/isolated/transfer` add field `type`
- `GET /sapi/v1/loan/vip/loanable/data` add new response fields `_flexibleDailyInterestRate`, `_flexibleYearlyInterestRate`
- `GET /sapi/v1/loan/vip/ongoing/orders`add new response fields `loanDate`，`loanRate`，`loanTerm`
- `POST /sapi/v1/portfolio/repay` add paramater `from`

### Deleted
- `GET /sapi/v1/futures/loan/borrow/history`
- `GET /sapi/v1/futures/loan/repay/history`
- `GET /sapi/v2/futures/loan/wallet`
- `GET /sapi/v1/futures/loan/adjustCollateral/history`
- `GET /sapi/v1/futures/loan/liquidationHistory`
- `GET /sapi/v1/futures/loan/interestHistory`


## 1.17.1 - 2023-09-19
### Changed
- Fixing typo

## 1.17.0 - 2023-09-19
### Added
- `GET /sapi/v1/simple-earn/flexible/list`
- `GET /sapi/v1/simple-earn/locked/list`
- `POST /sapi/v1/simple-earn/flexible/subscribe`
- `POST /sapi/v1/simple-earn/locked/subscribe`
- `POST /sapi/v1/simple-earn/flexible/redeem`
- `POST /sapi/v1/simple-earn/locked/redeem`
- `GET /sapi/v1/simple-earn/flexible/position`
- `GET /sapi/v1/simple-earn/locked/position`
- `GET /sapi/v1/simple-earn/account`
- `GET /sapi/v1/simple-earn/flexible/history/subscriptionRecord`
- `GET /sapi/v1/simple-earn/locked/history/subscriptionRecord`
- `GET /sapi/v1/simple-earn/flexible/history/redemptionRecord`
- `GET /sapi/v1/simple-earn/locked/history/redemptionRecord`
- `GET /sapi/v1/simple-earn/flexible/history/rewardsRecord`
- `GET /sapi/v1/simple-earn/locked/history/rewardsRecord`
- `POST /sapi/v1/simple-earn/flexible/setAutoSubscribe`
- `POST /sapi/v1/simple-earn/locked/setAutoSubscribe`
- `GET /sapi/v1/simple-earn/flexible/personalLeftQuota`
- `GET /sapi/v1/simple-earn/locked/personalLeftQuota`
- `GET /sapi/v1/simple-earn/flexible/subscriptionPreview`
- `GET /sapi/v1/simple-earn/locked/subscriptionPreview`
- `GET /sapi/v1/simple-earn/flexible/history/rateHistory`
- `GET /sapi/v1/simple-earn/flexible/history/collateralRecord`

### Removed
- `GET /sapi/v1/sub-account/apiRestrictions/ipRestriction/thirdPartyList`

## 1.16.0 - 2023-09-02
### Added
- `GET /sapi/v1/managed-subaccount/queryTransLogForInvestor`
- `GET /sapi/v1/managed-subaccount/queryTransLogForTradeParent`
- `GET /sapi/v1/managed-subaccount/fetch-future-asset`
- `GET /sapi/v1/managed-subaccount/marginAsset`
- `GET /sapi/v1/margin/crossMarginCollateralRatio`
- `GET /api/v3/myPreventedMatches`
- `GET /sapi/v1/margin/exchange-small-liability`
- `GET /sapi/v1/margin/exchange-small-liability-history`
- `GET /sapi/v4/sub-account/assets`
- `GET /sapi/v1/margin/next-hourly-interest-rate`
- `GET /sapi/v1/portfolio/interest-history`
- `GET /sapi/v1/managed-subaccount/info`
- `GET /sapi/v1/sub-account/transaction-statistics`
- `POST /sapi/v1/algo/spot/newOrderTwap`
- `DELETE /sapi/v1/algo/spot/order`
- `GET /sapi/v1/algo/spot/openOrders`
- `GET /sapi/v1/algo/spot/historicalOrders`
- `GET /sapi/v1/algo/spot/subOrders`
- `GET /sapi/v1/managed-subaccount/deposit/address`
- `GET /sapi/v1/portfolio/asset-index-price`
- `POST /sapi/v1/capital/deposit/credit-apply`
- `POST /sapi/v1/portfolio/auto-collection`
- `POST /sapi/v1/portfolio/bnb-transfer`
- `GET /sapi/v1/lending/auto-invest/target-asset/list`
- `GET /sapi/v1/lending/auto-invest/target-asset/roi/list`
- `GET /sapi/v1/lending/auto-invest/all/asset`
- `GET /sapi/v1/lending/auto-invest/source-asset/list`
- `POST /sapi/v1/lending/auto-invest/plan/add`
- `POST/sapi/v1/lending/auto-invest/plan/edit`
- `POST /sapi/v1/lending/auto-invest/plan/edit-status`
- `GET /sapi/v1/lending/auto-invest/plan/list`
- `GET /sapi/v1/lending/auto-invest/plan/id`
- `GET /sapi/v1/lending/auto-invest/history/list`
- `POST /sapi/v1/sub-account/eoptions/enable`
- `GET /sapi/v1/managed-subaccount/query-trans-log`
- `GET /sapi/v1/margin/dust`
- `POST /sapi/v1/margin/dust`
- `POST /sapi/v1/loan/vip/borrow`
- `GET /sapi/v1/loan/vip/loanable/data`
- `GET /sapi/v1/loan/vip/request/data`
- `POST /sapi/v1/margin/max-leverage`
- `POST /sapi/v1/portfolio/repay-futures-switch`
- `GET /sapi/v1/portfolio/repay-futures-switch`
- `POST /sapi/v1/portfolio/repay-futures-negative-balance`
- `POST /sapi/v1/loan/vip/renew`
- `POST /sapi/v1/portfolio/asset-collection`
- `POST /sapi/v1/loan/flexible/borrow`
- `GET /sapi/v1/loan/flexible/ongoing/orders`
- `GET /sapi/v1/loan/flexible/borrow/history`
- `POST /sapi/v1/loan/flexible/repay`
- `GET /sapi/v1/loan/flexible/repay/history`
- `POST /sapi/v1/loan/flexible/adjust/ltv`
- `GET /sapi/v1/loan/flexible/ltv/adjustment/history`
- `GET /sapi/v1/loan/flexible/loanable/data`
- `GET /sapi/v1/loan/flexible/collateral/data`

### Changed
- Add new fields `preventedMatchId` and `preventedQuantity` to :
  - `GET /api/v3/order`
  - `GET /api/v3/openOrders`
  - `GET /api/v3/allOrders`
- Add new optional parameter `selfTradePreventionMode` to:
  - `POST /api/v3/order`
  - `POST /api/v3/order/oco`
  - `POST /api/v3/order/cancelReplace`
- Add new optional parameter `cancelRestrictions` to:
  - `DELETE /api/v3/order`
  - `POST /api/v3/order/cancelReplace`
- Add `totalCollateralValueAfterHaircut` and `lockedCollateralValue` to `GET /sapi/v1/loan/vip/ongoing/orders`
- Add `preventSor` and `uid` to `GET /api/v3/account`
- Update security type from `MARKET_DATA` to `NONE` to `GET /api/v3/historicalTrades`
- Add `transactTime` to:
  - `DELETE /api/v3/order`
  - `POST /api/v3/order/cancelReplace`
  - `DELETE /api/v3/openOrders`
  - `DELETE /api/v3/orderList`
- Add `isFlexibleRate` to `POST /sapi/v1/loan/vip/borrow`
- Add `autoRepayAtCancel` and `selfTradePreventionMode` to `POST /sapi/v1/margin/order`
- Add `selfTradePreventionMode` to `POST /sapi/v1/margin/order/oco`

### Removed
- `GET /sapi/v1/lending/daily/product/list`
- `GET /sapi/v1/lending/daily/userLeftQuota`
- `POST /sapi/v1/lending/daily/purchase`
- `GET /sapi/v1/lending/daily/userRedemptionQuota`
- `POST /sapi/v1/lending/daily/redeem`
- `GET /sapi/v1/lending/daily/token/position`
- `GET /sapi/v1/lending/union/account`
- `GET /sapi/v1/lending/union/purchaseRecord`
- `GET /sapi/v1/lending/union/redemptionRecord`
- `GET /sapi/v1/lending/union/interestHistory`


## 1.15.0 - 2023-04-26
### Added
- New response fields `defaultSelfTradePreventionMode` and `allowedSelfTradePreventionModes` to `GET /api/v3/exchangeInfo`.
- New response field `selfTradePreventionMode` to the following endpoints:
  - `POST /api/v3/order`
  - `POST /api/v3/order/oco`
  - `POST /api/v3/order/cancelReplace`
  - `GET /api/v3/order`
  - `DELETE /api/v3/order`
  - `DELETE /api/v3/orderList`
- New response field `requireSelfTradePrevention` to `GET /api/v3/account`.
- New response field `workingTime` to the following endpoints:
  - `POST /api/v3/order`
  - `GET /api/v3/order`
  - `POST /api/v3/order/cancelReplace`
  - `POST /api/v3/order/oco`
  - `GET /api/v3/openOrders`
  - `GET /api/v3/allOrders`
- New response field `commissionRates` to `GET /api/v3/acccount`.


### Removed
- Discontinued endpoints `POST /sapi/v1/sub-account/subAccountApi/ipRestriction` and `POST /sapi/v1/sub-account/subAccountApi/ipRestriction/ipList`.

### Changed
- Replace `sufﬁcient` word (contains special character) with `sufficient`.

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

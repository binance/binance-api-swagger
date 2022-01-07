# Changelog

## 1.5.0 - 2021-01-07

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

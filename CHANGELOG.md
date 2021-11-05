# Changelog

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
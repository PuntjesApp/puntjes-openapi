# Changelog

## v2.0.0 (2026-10-12)

### API Changes

#### GET /campaigns
- :warning: added `#/components/schemas/TransactionCampaignConfigData, #/components/schemas/MomentCampaignConfigData, #/components/schemas/NthPurchaseCampaignConfigData, #/components/schemas/AnniversaryCampaignConfigData, #/components/schemas/WinBackCampaignConfigData, subschema #6` to the `data/data/items/config` response property `oneOf` list for the response status `200`
-  api operation id `v1.campaigns.index` removed and replaced with `listCampaigns`
-  api tag `Campaigns` added
-  api tag `ListCampaignsApiAction` removed
-  removed `#/components/schemas/TransactionCampaignConfigData, #/components/schemas/MomentCampaignConfigData, #/components/schemas/NthPurchaseCampaignConfigData, #/components/schemas/AnniversaryCampaignConfigData, #/components/schemas/WinBackCampaignConfigData, subschema #6` from the `data/data/items/config` response property `anyOf` list for the response status `200`
-  added discriminator to `data/data/items/config` response property for the response status `200`
-  added discriminator to `data/data/items/recurrence_config` response property for the response status `200`
-  added the required property `data/data/items/recurrence_config/oneOf[subschema #1: DateRangeRecurrenceData]/type` to the response with the `200` status
-  added the required property `data/data/items/recurrence_config/oneOf[subschema #2: DaysOfWeekRecurrenceData]/type` to the response with the `200` status
-  added the required property `data/data/items/recurrence_config/oneOf[subschema #3: SpecificDatesRecurrenceData]/type` to the response with the `200` status

#### POST /customers
-  api operation id `actions.createCustomerApiAction` removed and replaced with `registerCustomer`
-  api tag `Customers` added
-  api tag `CreateCustomerApiAction` removed
-  added the non-success response with the status `415`

#### PATCH /customers/by-external-id/{externalId}
-  endpoint added

#### PUT /customers/by-external-id/{externalId}
-  api operation id `actions.updateCustomerByExternalIdAction` removed and replaced with `replaceCustomerByExternalId`
-  api tag `Customers` added
-  api tag `UpdateCustomerByExternalIdAction` removed
-  added the non-success response with the status `409`
-  added the non-success response with the status `415`

#### POST /customers/by-external-id/{externalId}/send-card
-  api operation id `actions.sendLoyaltyCardByExternalIdApiAction` removed and replaced with `sendLoyaltyCardByExternalId`
-  api tag `Customers` added
-  api tag `SendLoyaltyCardByExternalIdApiAction` removed
-  added the non-success response with the status `415`

#### POST /customers/link-external-id
-  api operation id `actions.linkCustomerExternalIdAction` removed and replaced with `linkCustomerExternalId`
-  api tag `Customers` added
-  api tag `LinkCustomerExternalIdAction` removed
-  added the non-success response with the status `415`

#### GET /customers/lookup
-  api operation id `actions.lookupCustomerAction` removed and replaced with `lookupCustomer`
-  api tag `Customers` added
-  api tag `LookupCustomerAction` removed
-  added the optional property `data/is_deactivated` to the response with the `200` status
-  added the required property `data/wallet_balance` to the response with the `200` status

#### GET /customers/{customer}
-  api operation id `actions.showCustomerApiAction` removed and replaced with `showCustomer`
-  api tag `Customers` added
-  api tag `ShowCustomerApiAction` removed
-  added the optional property `data/is_deactivated` to the response with the `200` status

#### GET /customers/{customer}/ledger
-  api operation id `actions.listLedgerEntriesAction` removed and replaced with `listLedgerEntries`
-  api tag `Wallet` added
-  api tag `ListLedgerEntriesAction` removed

#### GET /customers/{customer}/redemptions
-  api operation id `actions.listRedemptionsApiAction` removed and replaced with `listCustomerRedemptions`
-  api tag `Redemptions` added
-  api tag `ListRedemptionsApiAction` removed
-  added the new enum value `cancelled` to the `query` request parameter `status`
-  added discriminator to `data/data/items/type_specific_data` response property for the response status `200`
-  added the required property `data/data/items/type_specific_data/oneOf[subschema #1: DiscountRedemptionData]/type` to the response with the `200` status
-  added the required property `data/data/items/type_specific_data/oneOf[subschema #2: FreeProductRedemptionData]/type` to the response with the `200` status

#### POST /customers/{customer}/send-card
-  api operation id `actions.sendLoyaltyCardApiAction` removed and replaced with `sendLoyaltyCard`
-  api tag `Customers` added
-  api tag `SendLoyaltyCardApiAction` removed
-  added the non-success response with the status `415`

#### GET /customers/{customer}/transactions
-  api operation id `actions.listTransactionsApiAction` removed and replaced with `listCustomerTransactions`
-  api tag `Transactions` added
-  api tag `ListTransactionsApiAction` removed

#### GET /customers/{customer}/vouchers
-  endpoint added

#### GET /customers/{customer}/wallet
-  api operation id `actions.showWalletAction` removed and replaced with `showWallet`
-  api tag `Wallet` added
-  api tag `ShowWalletAction` removed

#### GET /customers/{customer}/wallet-pass
-  api operation id `actions.downloadWalletPassAction` removed and replaced with `downloadWalletPass`
-  api tag `Wallet` added
-  api tag `DownloadWalletPassAction` removed
-  added the media type `application/vnd.apple.pkpass` for the response with the status `200`

#### POST /customers/{customer}/wallet/adjust
-  api operation id `actions.adjustWalletApiAction` removed and replaced with `adjustWallet`
-  api tag `Wallet` added
-  api tag `AdjustWalletApiAction` removed
-  added the non-success response with the status `415`

#### GET /health
-  api operation id `checkHealth` was added
-  api tag `Health` added

#### GET /me
-  api operation id `actions.showVendorBrandingAction` removed and replaced with `showMe`
-  api tag `Me` added
-  api tag `ShowVendorBrandingAction` removed

#### GET /products
-  api operation id `actions.listProductsApiAction` removed and replaced with `listProducts`
-  api tag `Products` added
-  api tag `ListProductsApiAction` removed

#### POST /products
-  api operation id `actions.createProductApiAction` removed and replaced with `createProduct`
-  api tag `Products` added
-  api tag `CreateProductApiAction` removed
-  added the non-success response with the status `415`

#### POST /products/batch
-  api operation id `actions.bulkUpsertProductsApiAction` removed and replaced with `bulkUpsertProducts`
-  api tag `Products` added
-  api tag `BulkUpsertProductsApiAction` removed
-  added the non-success response with the status `415`

#### DELETE /products/{externalId}
-  api operation id `actions.deleteProductApiAction` removed and replaced with `deleteProduct`
-  api tag `Products` added
-  api tag `DeleteProductApiAction` removed
-  added the non-success response with the status `415`

#### GET /products/{externalId}
-  api operation id `actions.showProductApiAction` removed and replaced with `showProduct`
-  api tag `Products` added
-  api tag `ShowProductApiAction` removed

#### PATCH /products/{externalId}
-  api operation id `actions.updateProductApiAction` removed and replaced with `updateProduct`
-  api tag `Products` added
-  api tag `UpdateProductApiAction` removed
-  added the non-success response with the status `415`

#### PUT /products/{externalId}
-  api operation id `actions.upsertProductApiAction` removed and replaced with `upsertProduct`
-  api tag `Products` added
-  api tag `UpsertProductApiAction` removed
-  added the non-success response with the status `415`

#### POST /products/{externalId}/reward
-  api operation id `actions.createRewardFromProductApiAction` removed and replaced with `createRewardFromProduct`
-  api tag `Products` added
-  api tag `CreateRewardFromProductApiAction` removed
-  added the new optional request property `idempotency_key`
-  added the new optional request property `max_redemptions_per_customer`
-  added the non-success response with the status `415`
-  added the required property `data/is_unlimited` to the response with the `201` status
-  added the required property `data/max_redemptions_per_customer` to the response with the `201` status

#### POST /redemptions
-  api operation id `actions.redeemRewardApiAction` removed and replaced with `redeemReward`
-  api tag `Redemptions` added
-  api tag `RedeemRewardApiAction` removed
-  added the non-success response with the status `415`
-  added discriminator to `data/type_specific_data` response property for the response status `201`
-  added the required property `data/type_specific_data/oneOf[subschema #1: DiscountRedemptionData]/type` to the response with the `201` status
-  added the required property `data/type_specific_data/oneOf[subschema #2: FreeProductRedemptionData]/type` to the response with the `201` status

#### GET /redemptions/{code}
-  api operation id `actions.lookupRedemptionAction` removed and replaced with `lookupRedemption`
-  api tag `Redemptions` added
-  api tag `LookupRedemptionAction` removed
-  added discriminator to `data/type_specific_data` response property for the response status `200`
-  added the required property `data/type_specific_data/oneOf[subschema #1: DiscountRedemptionData]/type` to the response with the `200` status
-  added the required property `data/type_specific_data/oneOf[subschema #2: FreeProductRedemptionData]/type` to the response with the `200` status

#### POST /redemptions/{code}/verify
-  api operation id `actions.verifyRedemptionApiAction` removed and replaced with `verifyRedemption`
-  api tag `Redemptions` added
-  api tag `VerifyRedemptionApiAction` removed
-  added the non-success response with the status `415`
-  added discriminator to `data/type_specific_data` response property for the response status `200`
-  added the required property `data/type_specific_data/oneOf[subschema #1: DiscountRedemptionData]/type` to the response with the `200` status
-  added the required property `data/type_specific_data/oneOf[subschema #2: FreeProductRedemptionData]/type` to the response with the `200` status

#### GET /rewards
-  api operation id `actions.listRewardsApiAction` removed and replaced with `listRewards`
-  api tag `Rewards` added
-  api tag `ListRewardsApiAction` removed
-  added the required property `data/items/customer_redemptions` to the response with the `200` status
-  added the required property `data/items/discount_type` to the response with the `200` status
-  added the required property `data/items/discount_value` to the response with the `200` status
-  added the required property `data/items/is_unlimited` to the response with the `200` status
-  added the required property `data/items/max_redemptions_per_customer` to the response with the `200` status

#### GET /statistics
-  api operation id `v1.statistics` removed and replaced with `showStatistics`
-  api tag `Statistics` added
-  api tag `ShowStatisticsApiAction` removed

#### POST /transactions
-  api operation id `actions.submitTransactionAction` removed and replaced with `submitTransaction`
-  api tag `Transactions` added
-  api tag `SubmitTransactionAction` removed
-  added the non-success response with the status `415`

#### GET /vouchers/{code}
-  endpoint added

#### POST /vouchers/{code}/verify
-  api operation id `actions.verifyCampaignVoucherApiAction` removed and replaced with `verifyVoucher`
-  api tag `Vouchers` added
-  api tag `VerifyCampaignVoucherApiAction` removed
-  added the new optional request property `idempotency_key`
-  added the non-success response with the status `415`
-  response property `data/discount/oneOf[subschema #1: VoucherPercentageDiscountData]/kind` deprecated
-  response property `data/discount/oneOf[subschema #2: VoucherFixedDiscountData]/kind` deprecated
-  added discriminator to `data/discount` response property for the response status `200`
-  added the required property `data/discount/oneOf[subschema #1: VoucherPercentageDiscountData]/type` to the response with the `200` status
-  added the required property `data/discount/oneOf[subschema #2: VoucherFixedDiscountData]/type` to the response with the `200` status
-  added the required property `data/products/items/product_reference` to the response with the `200` status

### Components
-  the component security scheme `oauth2` was added

### Security
-  the security scheme `oauth2` was added to the API

## v1.0.0 (2026-10-10)

First publication.

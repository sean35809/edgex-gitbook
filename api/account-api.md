# AccountPrivateApi

<a id="opIdupdateLeverageSetting"></a>

## POST Update Account Trading Leverage Settings

POST /api/v1/private/account/updateLeverageSetting

> Body Request Parameters

```json
{
  "accountId": "string",
  "contractId": "string",
  "leverage": "string"
}
```

### Request Parameters

| Name        | Location | Type                                    | Required | Description |
| ----------- | -------- | --------------------------------------- | -------- | ----------- |
| body        | body     | [UpdateLeverageSettingParam](#schemaupdateleveragesettingparam) | No       | none        |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": {},
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | Inline     |

### Response Data Structure

<a id="opIdupdateFeeSetting"></a>

## POST Update Account Trading Fee Settings

POST /api/v1/private/account/updateFeeSetting

> Body Request Parameters

```json
{
  "accountId": "string",
  "contractId": "string",
  "isSetFeeRate": true,
  "takerFeeRate": "string",
  "makerFeeRate": "string",
  "isSetFeeDiscount": true,
  "takerFeeDiscount": "string",
  "makerFeeDiscount": "string"
}
```

### Request Parameters

| Name        | Location | Type                                | Required | Description |
| ----------- | -------- | ----------------------------------- | -------- | ----------- |
| body        | body     | [UpdateFeeSettingParam](#schemaupdatefeesettingparam) | No       | none        |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": {},
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | Inline     |

### Response Data Structure

<a id="opIdregisterAccount"></a>

## POST Register Account

POST /api/v1/private/account/registerAccount

> Body Request Parameters

```json
{
  "l2Key": "string",
  "l2KeyYCoordinate": "string",
  "clientAccountId": "string"
}
```

### Request Parameters

| Name        | Location | Type                            | Required | Description |
| ----------- | -------- | ------------------------------- | -------- | ----------- |
| body        | body     | [RegisterAccountParam](#schemaregisteraccountparam) | No       | none        |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": {
    "accountId": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | Inline     |

### Response Data Structure

<a id="opIdgetPositionTransactionPage"></a>

## GET Get Position Transaction Page

GET /api/v1/private/account/getPositionTransactionPage

### Request Parameters

| Name                            | Location | Type   | Required | Description                                                                                                |
| ------------------------------- | -------- | ------ | -------- | ---------------------------------------------------------------------------------------------------------- |
| accountId                       | query    | string | No       | Account ID                                                                                                 |
| size                            | query    | string | No       | Number of items to retrieve. Must be greater than 0 and less than or equal to 100                             |
| offsetData                      | query    | string | No       | Pagination offset. If empty or not provided, the first page is retrieved                                     |
| filterCoinIdList                | query    | string | No       | Filter position transaction records by specified coin IDs. If not provided, all collateral transaction records are retrieved |
| filterContractIdList            | query    | string | No       | Filter position transaction records by specified contract IDs. If not provided, all position transaction records are retrieved|
| filterTypeList                  | query    | string | No       | Filter position transaction records by specified types. If not provided, all position transaction records are retrieved|
| filterStartCreatedTimeInclusive | query    | string | No       | Filter position transaction records created after or at the specified start time (inclusive). If not provided or 0, retrieves records from the earliest time |
| filterEndCreatedTimeExclusive   | query    | string | No       | Filter position transaction records created before the specified end time (exclusive). If not provided or 0, retrieves records up to the latest time    |
| filterCloseOnly                 | query    | string | No       | Whether to return only position transactions that include closing positions.  `true`: only return records with closing; `false`: return all records|
| filterOpenOnly                  | query    | string | No       | Whether to return only position transactions that include opening positions. `true`: only return records with opening; `false`: return all records|

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | [Result](#schemaresult) |

<a id="opIdgetPositionTransactionById"></a>

## GET Get Position Transactions By Account ID and Transaction ID

GET /api/v1/private/account/getPositionTransactionById

### Request Parameters

| Name                      | Location | Type   | Required | Description         |
| ------------------------- | -------- | ------ | -------- | ------------------- |
| accountId                 | query    | string | No       | Account ID          |
| positionTransactionIdList | query    | string | No       | Position Transaction IDs |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | [Result](#schemaresult) |

<a id="opIdgetPositionTermPage"></a>

## GET Get Position Term Page by Account ID

GET /api/v1/private/account/getPositionTermPage

### Request Parameters

| Name                            | Location | Type   | Required | Description                                                                                               |
| ------------------------------- | -------- | ------ | -------- | --------------------------------------------------------------------------------------------------------- |
| accountId                       | query    | string | No       | Account ID                                                                                                |
| size                            | query    | string | No       | Number of items to retrieve. Must be greater than 0 and less than or equal to 100                             |
| offsetData                      | query    | string | No       | Pagination offset. If empty or not provided, the first page is retrieved                                     |
| filterCoinIdList                | query    | string | No       | Filter position term records by specified coin IDs. If not provided, all position term records are retrieved |
| filterContractIdList            | query    | string | No       | Filter position term records by specified contract IDs. If not provided, all position term records are retrieved |
| filterIsLongPosition            | query    | string | No       | Filter position term records by position direction. If not provided, all position term records are retrieved |
| filterStartCreatedTimeInclusive | query    | string | No       | Filter position term records created after or at the specified start time (inclusive). If not provided or 0, retrieves records from the earliest time |
| filterEndCreatedTimeExclusive   | query    | string | No       | Filter position term records created before the specified end time (exclusive). If not provided or 0, retrieves records up to the latest time    |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | [Result](#schemaresult) |

<a id="opIdgetCollateralByCoinId"></a>

## GET Get Position By Account ID and Contract ID

GET /api/v1/private/account/getPositionByContractId

### Request Parameters

| Name           | Location | Type   | Required | Description        |
| -------------- | -------- | ------ | -------- | ------------------ |
| accountId      | query    | string | No       | Account ID         |
| contractIdList | query    | string | No       | Specified contract IDs |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "openSize": "string",
      "openValue": "string",
      "openFee": "string",
      "fundingFee": "string",
      "longTermCount": 0,
      "longTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "longTermCreatedTime": "string",
      "longTermUpdatedTime": "string",
      "shortTermCount": 0,
      "shortTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTermCreatedTime": "string",
      "shortTermUpdatedTime": "string",
      "longTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | Inline     |

### Response Data Structure

<a id="opIdgetCollateralTransactionPage"></a>

## GET Get Collateral Transaction Page by Account ID

GET /api/v1/private/account/getCollateralTransactionPage

### Request Parameters

| Name                            | Location | Type   | Required | Description                                                                                             |
| ------------------------------- | -------- | ------ | -------- | --------------------------------------------------------------------------------------------------------- |
| accountId                       | query    | string | No       | Account ID                                                                                                |
| size                            | query    | string | No       | Number of items to retrieve. Must be greater than 0 and less than or equal to 100                             |
| offsetData                      | query    | string | No       | Pagination offset. If empty or not provided, the first page is retrieved                                     |
| filterCoinIdList                | query    | string | No       | Filter collateral transaction records by specified coin IDs. If not provided, all collateral transaction records are retrieved |
| filterTypeList                  | query    | string | No       | Filter collateral transaction records by specified transaction types. If not provided, all collateral transaction records are retrieved |
| filterStartCreatedTimeInclusive | query    | string | No       | Filter collateral transaction records created after or at the specified start time (inclusive). If not provided or 0, retrieves records from the earliest time |
| filterEndCreatedTimeExclusive   | query    | string | No       | Filter collateral transaction records created before the specified end time (exclusive). If not provided or 0, retrieves records up to the latest time    |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
        "deltaAmount": "string",
        "deltaLegacyAmount": "string",
        "beforeAmount": "string",
        "beforeLegacyAmount": "string",
        "fillCloseSize": "string",
        "fillCloseValue": "string",
        "fillCloseFee": "string",
        "fillOpenSize": "string",
        "fillOpenValue": "string",
        "fillOpenFee": "string",
        "fillPrice": "string",
        "liquidateFee": "string",
        "realizePnl": "string",
        "isLiquidate": true,
        "isDeleverage": true,
        "fundingTime": "string",
        "fundingRate": "string",
        "fundingIndexPrice": "string",
        "fundingOraclePrice": "string",
        "fundingPositionSize": "string",
        "depositId": "string",
        "withdrawId": "string",
        "transferInId": "string",
        "transferOutId": "string",
        "transferReason": "UNKNOWN_TRANSFER_REASON",
        "orderId": "string",
        "orderFillTransactionId": "string",
        "orderAccountId": "string",
        "positionContractId": "string",
        "positionTransactionId": "string",
        "forceWithdrawId": "string",
        "forceTradeId": "string",
        "extraType": "string",
        "extraDataJson": "string",
        "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
        "censorTxId": "string",
        "censorTime": "string",
        "censorFailCode": "string",
        "censorFailReason": "string",
        "l2TxId": "string",
        "l2RejectTime": "string",
        "l2RejectCode": "string",
        "l2RejectReason": "string",
        "l2ApprovedTime": "string",
        "createdTime": "string",
        "updatedTime": "string"
      }
    ],
    "nextPageOffsetData": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | Inline     |

### Response Data Structure

<a id="opIdgetCollateralTransactionById"></a>

## GET Get Collateral Transactions By Account ID and Transaction ID

GET /api/v1/private/account/getCollateralTransactionById

### Request Parameters

| Name                        | Location | Type   | Required | Description         |
| --------------------------- | -------- | ------ | -------- | ------------------- |
| accountId                   | query    | string | No       | Account ID          |
| collateralTransactionIdList | query    | string | No       | Collateral Transaction IDs |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
      "deltaAmount": "string",
      "deltaLegacyAmount": "string",
      "beforeAmount": "string",
      "beforeLegacyAmount": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "depositId": "string",
      "withdrawId": "string",
      "transferInId": "string",
      "transferOutId": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "orderAccountId": "string",
      "positionContractId": "string",
      "positionTransactionId": "string",
      "forceWithdrawId": "string",
      "forceTradeId": "string",
      "extraType": "string",
      "extraDataJson": "string",
      "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2RejectTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l2ApprovedTime": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | Inline     |

### Response Data Structure

<a id="opIdgetCollateralByCoinId_1"></a>

## GET Get Collateral By Account ID and Coin ID

GET /api/v1/private/account/getCollateralByCoinId

### Request Parameters

| Name        | Location | Type   | Required | Description                                                                                      |
| ----------- | -------- | ------ | -------- | ------------------------------------------------------------------------------------------------ |
| accountId   | query    | string | No       | Account ID                                                                                       |
| coinIdList  | query    | string | No       | Filter collateral information by specified coin IDs. If not provided, all collateral information is retrieved |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "amount": "string",
      "legacyAmount": "string",
      "cumDepositAmount": "string",
      "cumWithdrawAmount": "string",
      "cumTransferInAmount": "string",
      "cumTransferOutAmount": "string",
      "cumPositionBuyAmount": "string",
      "cumPositionSellAmount": "string",
      "cumFillFeeAmount": "string",
      "cumFundingFeeAmount": "string",
      "cumFillFeeIncomeAmount": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | Inline     |

### Response Data Structure

<a id="opIdgetAccountPage"></a>

## GET Get Account Page by User ID

GET /api/v1/private/account/getAccountPage

### Request Parameters

| Name       | Location | Type   | Required | Description                                                                                   |
| ---------- | -------- | ------ | -------- | --------------------------------------------------------------------------------------------- |
| size       | query    | string | No       | Number of items to retrieve. Must be greater than 0 and less than or equal to 100                 |
| offsetData | query    | string | No       | Pagination offset. If empty or not provided, the first page is retrieved                       |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | [Result](#schemaresult) |

<a id="opIdgetAccountDeleverageLight"></a>

## GET Get Account Deleverage Light

GET /api/v1/private/account/getAccountDeleverageLight

### Request Parameters

| Name      | Location | Type   | Required | Description |
| --------- | -------- | ------ | -------- | ----------- |
| accountId | query    | string | No       | Account ID  |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | [Result](#schemaresult) |

<a id="opIdgetAccountById"></a>

## GET Get Account By Account ID

GET /api/v1/private/account/getAccountById

### Request Parameters

| Name      | Location | Type   | Required | Description |
| --------- | -------- | ------ | -------- | ----------- |
| accountId | query    | string | No       | Account ID  |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | [Result](#schemaresult) |

<a id="opIdgetAccountAsset"></a>

## GET Get Account Asset

GET /api/v1/private/account/getAccountAsset

### Request Parameters

| Name      | Location | Type   | Required | Description |
| --------- | -------- | ------ | -------- | ----------- |
| accountId | query    | string | No       | Account ID  |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ---------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | [Result](#schemaresult) |

<a id="opIdgetAccountAssetSnapshotPage"></a>

## GET Get Account Asset Snapshot Page by Account ID

GET /api/v1/private/account/getAccountAssetSnapshotPage

### Request Parameters

| Name                       | Location | Type   | Required | Description                                                                                                   |
| -------------------------- | -------- | ------ | -------- | --------------------------------------------------------------------------------
| accountId                | query    | string | No       | Account ID                                                                                                    |
| size                     | query    | string | No       | Number of items to retrieve. Must be greater than 0 and less than or equal to 1000                             |
| offsetData               | query    | string | No       | Pagination offset. If empty or not provided, the first page is retrieved                                         |
| coinId                   | query    | string | Yes      | Filter by the specified coin ID.                                                                               |
| filterTimeTag            | query    | string | No       | Specifies time tag. If not provided or 0, returns snapshots by the hour. 1 returns snapshots by the day      |
| filterStartTimeInclusive | query    | string | No       | Filter snapshots created after or at the specified start time (inclusive). If not provided or 0, retrieves records from the earliest time |
| filterEndTimeExclusive   | query    | string | No       | Filter snapshots created before the specified end time (exclusive). If not provided or 0, retrieves records up to the latest time  |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

| Status Code | Status Code Description                                                                  | Description        | Data Model                                        |
| ----------- | ---------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                                  | default response | [Result&lt;PageData&lt;AccountAssetSnapshot&gt;&gt;](#schemaresult<pagedata<accountassetsnapshot>>) |

# Data Models

<h2 id="tocS_Result<PageData<AccountAssetSnapshot>>">Result&lt;PageData&lt;AccountAssetSnapshot&gt;&gt;</h2>

<a id="schemaresult<pagedata<accountassetsnapshot>>"></a>
<a id="schema_Result<PageData<AccountAssetSnapshot>>"></a>
<a id="tocSresult<pagedata<accountassetsnapshot>>"></a>
<a id="tocsresult<pagedata<accountassetsnapshot>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "timeTag": 0,
        "snapshotTime": "string",
        "totalEquity": "string",
        "termRealizePnl": "string",
        "unrealizePnl": "string",
        "totalRealizePnl": "string"
      }
    ],
    "nextPageOffsetData": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                               | Required | Constraints | Description              | Notes                                                                    |
| -------------- | ---------------------------------- | -------- | ----------- | ------------------------ | ------------------------------------------------------------------------ |
| code           | string                             | false    | none        | Status Code              | Returns "SUCCESS" on success; otherwise, it indicates failure.            |
| data           | [PageDataAccountAssetSnapshot](#schemapagedataaccountassetsnapshot) | false    | none        | Generic Paginated Response |                                                                          |
| errorParam     | object                             | false    | none        | Error Parameters         | Error message parameter information                                       |
| » **additionalProperties** | string                                | false    | none        | Error Parameters         | Error message parameter information                                       |
| requestTime    | string(timestamp)                  | false    | none        | Server Request Time     | Time at which the server received the request                             |
| responseTime   | string(timestamp)                  | false    | none        | Server Response Time    | Time at which the server sent the response                                |
| traceId        | string                             | false    | none        | Trace ID                | Invocation trace ID                                                     |

<h2 id="tocS_PageDataAccountAssetSnapshot">PageDataAccountAssetSnapshot</h2>

<a id="schemapagedataaccountassetsnapshot"></a>
<a id="schema_PageDataAccountAssetSnapshot"></a>
<a id="tocSpagedataaccountassetsnapshot"></a>
<a id="tocspagedataaccountassetsnapshot"></a>

```json
{
  "dataList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "timeTag": 0,
      "snapshotTime": "string",
      "totalEquity": "string",
      "termRealizePnl": "string",
      "unrealizePnl": "string",
      "totalRealizePnl": "string"
    }
  ],
  "nextPageOffsetData": "string"
}
```

Generic Paginated Response

### Properties

| Name               | Type                               | Required | Constraints | Description                 | Notes                                                               |
| ------------------ | ---------------------------------- | -------- | ----------- | --------------------------- | ------------------------------------------------------------------- |
| dataList           | [[AccountAssetSnapshot](#schemaaccountassetsnapshot)] | false    | none        | Data List                  |                                                                     |
| nextPageOffsetData | string                             | false    | none        | Next Page Offset        | Offset for retrieving the next page. If no next page data, empty string. |

<h2 id="tocS_AccountAssetSnapshot">AccountAssetSnapshot</h2>

<a id="schemaaccountassetsnapshot"></a>
<a id="schema_AccountAssetSnapshot"></a>
<a id="tocSaccountassetsnapshot"></a>
<a id="tocsaccountassetsnapshot"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "timeTag": 0,
  "snapshotTime": "string",
  "totalEquity": "string",
  "termRealizePnl": "string",
  "unrealizePnl": "string",
  "totalRealizePnl": "string"
}
```

Account historical asset snapshot information.

### Properties

| Name             | Type            | Required | Constraints | Description                         | Notes                                                                     |
| ---------------- | --------------- | -------- | ----------- | ----------------------------------- | ------------------------------------------------------------------------- |
| userId           | string(int64)   | false    | none        | User ID                             | ID of the owning user                                                  |
| accountId        | string(int64)   | false    | none        | Account ID                          | ID of the owning account                                                 |
| coinId           | string(int64)   | false    | none        | Collateral Coin ID                 | ID of the associated collateral coin                                        |
| timeTag          | integer(int32)  | false    | none        | Time Tag                            | Time tag. 1 represents the snapshot time is for the whole day.           |
| snapshotTime     | string(int64)   | false    | none        | Snapshot Time                       | Snapshot time, hourly timestamp at the top of the hour.                  |
| totalEquity      | string          | false    | none        | Total Collateral Value              | Current total value of the collateral                                      |
| termRealizePnl  | string          | false    | none        | Term Realized PnL                   | Realized PnL for the term                                               |
| unrealizePnl     | string          | false    | none        | Unrealized PnL                      | Unrealized PnL                                                            |
| totalRealizePnl  | string          | false    | none        | Total Realized PnL                 | Total realized PnL of the position                                          |

<h2 id="tocS_Result<GetAccountAsset>">Result&lt;GetAccountAsset&gt;</h2>

<a id="schemaresult<getaccountasset>"></a>
<a id="schema_Result<GetAccountAsset>"></a>
<a id="tocSresult<getaccountasset>"></a>
<a id="tocsresult<getaccountasset>"></a>

```json
{
  "code": "string",
  "data": {
    "account": {
      "id": "string",
      "userId": "string",
      "ethAddress": "string",
      "l2Key": "string",
      "l2KeyYCoordinate": "string",
      "clientAccountId": "string",
      "isSystemAccount": true,
      "defaultTradeSetting": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      },
      "contractIdToTradeSetting": {
        "property1": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        },
        "property2": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        }
      },
      "maxLeverageLimit": "string",
      "createOrderPerMinuteLimit": 0,
      "createOrderDelayMillis": 0,
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ACCOUNT_STATUS",
      "isLiquidating": true,
      "createdTime": "string",
      "updatedTime": "string"
    },
    "collateralList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "amount": "string",
        "legacyAmount": "string",
        "cumDepositAmount": "string",
        "cumWithdrawAmount": "string",
        "cumTransferInAmount": "string",
        "cumTransferOutAmount": "string",
        "cumPositionBuyAmount": "string",
        "cumPositionSellAmount": "string",
        "cumFillFeeAmount": "string",
        "cumFundingFeeAmount": "string",
        "cumFillFeeIncomeAmount": "string",
        "createdTime": "string",
        "updatedTime": "string"
      }
    ],
    "positionList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "openSize": "string",
        "openValue": "string",
        "openFee": "string",
        "fundingFee": "string",
        "longTermCount": 0,
        "longTermStat": {
          "cumOpenSize": "string",
          "cumOpenValue": "string",
          "cumOpenFee": "string",
          "cumCloseSize": "string",
          "cumCloseValue": "string",
          "cumCloseFee": "string",
          "cumFundingFee": "string",
          "cumLiquidateFee": "string"
        },
        "longTermCreatedTime": "string",
        "longTermUpdatedTime": "string",
        "shortTermCount": 0,
        "shortTermStat": {
          "cumOpenSize": "string",
          "cumOpenValue": "string",
          "cumOpenFee": "string",
          "cumCloseSize": "string",
          "cumCloseValue": "string",
          "cumCloseFee": "string",
          "cumFundingFee": "string",
          "cumLiquidateFee": "string"
        },
        "shortTermCreatedTime": "string",
        "shortTermUpdatedTime": "string",
        "longTotalStat": {
          "cumOpenSize": "string",
          "cumOpenValue": "string",
          "cumOpenFee": "string",
          "cumCloseSize": "string",
          "cumCloseValue": "string",
          "cumCloseFee": "string",
          "cumFundingFee": "string",
          "cumLiquidateFee": "string"
        },
        "shortTotalStat": {
          "cumOpenSize": "string",
          "cumOpenValue": "string",
          "cumOpenFee": "string",
          "cumCloseSize": "string",
          "cumCloseValue": "string",
          "cumCloseFee": "string",
          "cumFundingFee": "string",
          "cumLiquidateFee": "string"
        },
        "createdTime": "string",
        "updatedTime": "string"
      }
    ],
    "version": "string",
    "positionAssetList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "positionValue": "string",
        "maxLeverage": "string",
        "initialMarginRequirement": "string",
        "starkExRiskRate": "string",
        "starkExRiskValue": "string",
        "avgEntryPrice": "string",
        "liquidatePrice": "string",
        "bankruptPrice": "string",
        "worstClosePrice": "string",
        "unrealizePnl": "string",
        "termRealizePnl": "string",
        "totalRealizePnl": "string"
      }
    ],
    "collateralAssetModelList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "totalEquity": "string",
        "totalPositionValueAbs": "string",
        "initialMarginRequirement": "string",
        "starkExRiskValue": "string",
        "pendingWithdrawAmount": "string",
        "pendingTransferOutAmount": "string",
        "orderFrozenAmount": "string",
        "availableAmount": "string"
      }
    ],
    "oraclePriceList": [
      {
        "contractId": "string",
        "priceType": "UNKNOWN_PRICE_TYPE",
        "priceValue": "string",
        "createdTime": "string",
        "oraclePriceSignature": [
          {
            "contractId": null,
            "signer": null,
            "price": null,
            "externalAssetId": null,
            "signature": null,
            "timestamp": null
          }
        ]
      }
    ]
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                            | Required | Constraints | Description              | Notes                                                                  |
| -------------- | ------------------------------- | -------- | ----------- | ------------------------ | ---------------------------------------------------------------------- |
| code           | string                          | false    | none        | Status Code              | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [GetAccountAsset](#schemagetaccountasset) | false    | none        | Get Account Asset Response | Response structure for fetching account asset data.                       |
| errorParam     | object                          | false    | none        | Error Parameters         | Error message parameter information                                     |
| » **additionalProperties** | string                               | false    | none        | Error Parameters         | Error message parameter information                                     |
| requestTime    | string(timestamp)               | false    | none        | Server Request Time     | Time at which the server received the request                           |
| responseTime   | string(timestamp)               | false    | none        | Server Response Time    | Time at which the server sent the response                              |
| traceId        | string                          | false    | none        | Trace ID                | Invocation trace ID                                                  |

<h2 id="tocS_GetAccountAsset">GetAccountAsset</h2>

<a id="schemagetaccountasset"></a>
<a id="schema_GetAccountAsset"></a>
<a id="tocSgetaccountasset"></a>
<a id="tocsgetaccountasset"></a>

```json
{
  "account": {
    "id": "string",
    "userId": "string",
    "ethAddress": "string",
    "l2Key": "string",
    "l2KeyYCoordinate": "string",
    "clientAccountId": "string",
    "isSystemAccount": true,
    "defaultTradeSetting": {
      "isSetFeeRate": true,
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "isSetFeeDiscount": true,
      "takerFeeDiscount": "string",
      "makerFeeDiscount": "string",
      "isSetMaxLeverage": true,
      "maxLeverage": "string"
    },
    "contractIdToTradeSetting": {
      "property1": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      },
      "property2": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      }
    },
    "maxLeverageLimit": "string",
    "createOrderPerMinuteLimit": 0,
    "createOrderDelayMillis": 0,
    "extraType": "string",
    "extraDataJson": "string",
    "status": "UNKNOWN_ACCOUNT_STATUS",
    "isLiquidating": true,
    "createdTime": "string",
    "updatedTime": "string"
  },
  "collateralList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "amount": "string",
      "legacyAmount": "string",
      "cumDepositAmount": "string",
      "cumWithdrawAmount": "string",
      "cumTransferInAmount": "string",
      "cumTransferOutAmount": "string",
      "cumPositionBuyAmount": "string",
      "cumPositionSellAmount": "string",
      "cumFillFeeAmount": "string",
      "cumFundingFeeAmount": "string",
      "cumFillFeeIncomeAmount": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "positionList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "openSize": "string",
      "openValue": "string",
      "openFee": "string",
      "fundingFee": "string",
      "longTermCount": 0,
      "longTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "longTermCreatedTime": "string",
      "longTermUpdatedTime": "string",
      "shortTermCount": 0,
      "shortTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTermCreatedTime": "string",
      "shortTermUpdatedTime": "string",
      "longTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "version": "string",
  "positionAssetList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "positionValue": "string",
      "maxLeverage": "string",
      "initialMarginRequirement": "string",
      "starkExRiskRate": "string",
      "starkExRiskValue": "string",
      "avgEntryPrice": "string",
      "liquidatePrice": "string",
      "bankruptPrice": "string",
      "worstClosePrice": "string",
      "unrealizePnl": "string",
      "termRealizePnl": "string",
      "totalRealizePnl": "string"
    }
  ],
  "collateralAssetModelList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "totalEquity": "string",
      "totalPositionValueAbs": "string",
      "initialMarginRequirement": "string",
      "starkExRiskValue": "string",
      "pendingWithdrawAmount": "string",
      "pendingTransferOutAmount": "string",
      "orderFrozenAmount": "string",
      "availableAmount": "string"
    }
  ],
  "oraclePriceList": [
    {
      "contractId": "string",
      "priceType": "UNKNOWN_PRICE_TYPE",
      "priceValue": "string",
      "createdTime": "string",
       "oraclePriceSignature": [
        {
            "contractId": "string",
            "signer": "string",
            "price": "string",
            "externalAssetId": "string",
            "signature": {
                "r": "string",
                "s": "string",
                "v": "string"
            },
            "timestamp": "string"
        }
    ]
    }
  ]
}
```

Response structure for fetching account asset data.

### Properties

| Name                  | Type                                | Required | Constraints | Description                                                                                      | Notes                                                                                          |
| --------------------- | ----------------------------------- | -------- | ----------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| account               | [Account](#schemaaccount)           | false    | none        | Account Information                                                                              | Account information data.                                                                  |
| collateralList        | [[Collateral](#schemacollateral)]   | false    | none        | Collateral Information List                                                                   | List of collateral information data.                                                           |
| positionList          | [[Position](#schemaposition)]       | false    | none        | Perpetual Contract Position List                                                                 | List of perpetual contract position information.                                               |
| version               | string(int64)                       | false    | none        | Account Version                                                                                | Account version number, incremented with each update.                                        |
| positionAssetList     | [[PositionAsset](#schemapositionasset)] | false    | none        | Position Asset Information List                                                                  | List of position asset information.                                                              |
| collateralAssetModelList | [[CollateralAsset](#schemacollateralasset)] | false    | none        | Account-Level Asset Information List                                                               | List of account-level asset information.                                                          |
| oraclePriceList       | [[IndexPrice](#schemaindexprice)]   | false    | none        | Oracle Price List                                                  | List of all oracle prices used to calculate assets (only those used).                                                          |

<h2 id="tocS_IndexPrice">IndexPrice</h2>

<a id="schemaindexprice"></a>
<a id="schema_IndexPrice"></a>
<a id="tocSindexprice"></a>
<a id="tocsindexprice"></a>

```json
{
  "contractId": "string",
  "priceType": "UNKNOWN_PRICE_TYPE",
  "priceValue": "string",
  "createdTime": "string",
  "oraclePriceSignature": [
    {
      "contractId": "string",
      "signer": "string",
      "price": "string",
      "externalAssetId": "string",
      "signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "timestamp": "string"
    }
  ]
}
```

Price information

### Properties

| Name                  | Type                  | Required | Constraints | Description                        | Notes                                                                            |
| --------------------- | --------------------- | -------- | ----------- | ---------------------------------- | -------------------------------------------------------------------------------- |
| contractId            | string(int64)         | false    | none        | Contract ID                        | Contract ID                                                                      |
| priceType             | string                | false    | none        | Price Type                         |                                                                                  |
| priceValue            | string                | false    | none        | Price Value                        | Price value                                                                      |
| createdTime           | string(int64)         | false    | none        | Creation Time                      | Time of creation                                                                 |
| oraclePriceSignature  | [[OraclePriceSignature](#schemaoraclepricesignature)] | false    | none        | Oracle Price Signature Information | Oracle price signature information, only exists when price_type=ORACLE_PRICE. |

#### Enumerated Values

| Property  | Value                     |
| --------- | ------------------------- |
| priceType | UNKNOWN_PRICE_TYPE        |
| priceType | ORACLE_PRICE            |
| priceType | INDEX_PRICE               |
| priceType | LAST_PRICE                |
| priceType | ASK1_PRICE                |
| priceType | BID1_PRICE                |
| priceType | OPEN_INTEREST             |
| priceType | UNRECOGNIZED              |

<h2 id="tocS_OraclePriceSignature">OraclePriceSignature</h2>

<a id="schemaoraclepricesignature"></a>
<a id="schema_OraclePriceSignature"></a>
<a id="tocSoraclepricesignature"></a>
<a id="tocsoraclepricesignature"></a>

```json
{
  "contractId": "string",
  "signer": "string",
  "price": "string",
  "externalAssetId": "string",
  "signature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "timestamp": "string"
}
```

Oracle price signature information.

### Properties

| Name             | Type                    | Required | Constraints | Description                                                              | Notes                                                                                                    |
| ---------------- | ----------------------- | -------- | ----------- | ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| contractId       | string(int64)           | false    | none        | Contract ID                                                              | Contract ID                                                                                            |
| signer           | string                  | false    | none        | Signer ID                                                                | Signer identifier                                                                                        |
| price            | string                  | false    | none        | Signed Price                                                             | The price signed (price after stark ex precision processing)                                                    |
| externalAssetId  | string                  | false    | none        | Concatenated Asset and Oracle Names        | Concatenation of the asset name and the oracle name (both in hex encoding).                                               |
| signature        | [L2Signature](#schemal2signature) | false    | none        | L2 Signature Information                                            | L2 signature information                                                                               |
| timestamp        | string(int64)           | false    | none        | Signature Creation Time                                                | The time the signature was created.                                                                     |

<h2 id="tocS_L2Signature">L2Signature</h2>

<a id="schemal2signature"></a>
<a id="schema_L2Signature"></a>
<a id="tocSl2signature"></a>
<a id="tocsl2signature"></a>

```json
{
  "r": "string",
  "s": "string",
  "v": "string"
}
```

L2 signature information.

### Properties

| Name | Type   | Required | Constraints | Description      | Notes                  |
| ---- | ------ | -------- | ----------- | ---------------- | ---------------------- |
| r    | string | false    | none        | R Value          | Bigint for hex string |
| s    | string | false    | none        | S Value          | Bigint for hex string |
| v    | string | false    | none        | V Value          | Bigint for hex string |

<h2 id="tocS_CollateralAsset">CollateralAsset</h2>

<a id="schemacollateralasset"></a>
<a id="schema_CollateralAsset"></a>
<a id="tocScollateralasset"></a>
<a id="tocscollateralasset"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "totalEquity": "string",
  "totalPositionValueAbs": "string",
  "initialMarginRequirement": "string",
  "starkExRiskValue": "string",
  "pendingWithdrawAmount": "string",
  "pendingTransferOutAmount": "string",
  "orderFrozenAmount": "string",
  "availableAmount": "string"
}
```

Collateral asset information.

### Properties

| Name                    | Type          | Required | Constraints | Description                                                                      | Notes                                                                              |
| ----------------------- | ------------- | -------- | ----------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| userId                  | string(int64) | false    | none        | User ID                                                                          | ID of the owning user.                                                               |
| accountId               | string(int64) | false    | none        | Account ID                                                                       | ID of the owning account.                                                              |
| coinId                  | string(int64) | false    | none        | Collateral Coin ID                                                               | ID of the associated collateral coin.                                                  |
| totalEquity             | string        | false    | none        | Total Collateral Value                                                           | Current total value of the collateral.                                                |
| totalPositionValueAbs    | string        | false    | none        | Sum of Absolute Position Values                                                     | Sum of the absolute position values for the current collateral                        |
| initialMarginRequirement| string        | false    | none        | Initial Margin Requirement                                                     | The initial margin requirement for the current collateral.                              |
| starkExRiskValue        | string        | false    | none        | Total StarkEx Risk Value                                                           | The total starkEx risk amount for the current collateral.                             |
| pendingWithdrawAmount  | string        | false    | none        | Pending Withdrawal Amount                                                      | The amount of collateral pending withdrawal.                                          |
| pendingTransferOutAmount| string        | false    | none        | Pending Transfer Out Amount                                                     | The amount of collateral pending transfer out.                                       |
| orderFrozenAmount       | string        | false    | none        | Order Frozen Amount                                                             | The amount of collateral frozen by orders.                                            |
| availableAmount         | string        | false    | none        | Available Amount                                                                | The amount of collateral available for use.                                           |

<h2 id="tocS_PositionAsset">PositionAsset</h2>

<a id="schemapositionasset"></a>
<a id="schema_PositionAsset"></a>
<a id="tocSpositionasset"></a>
<a id="tocspositionasset"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "positionValue": "string",
  "maxLeverage": "string",
  "initialMarginRequirement": "string",
  "starkExRiskRate": "string",
  "starkExRiskValue": "string",
  "avgEntryPrice": "string",
  "liquidatePrice": "string",
  "bankruptPrice": "string",
  "worstClosePrice": "string",
  "unrealizePnl": "string",
  "termRealizePnl": "string",
  "totalRealizePnl": "string"
}
```

Asset information related to a position

### Properties

| Name                    | Type          | Required | Constraints | Description                            | Notes                                                                          |
| ----------------------- | ------------- | -------- | ----------- | -------------------------------------- | ------------------------------------------------------------------------------ |
| userId                  | string(int64) | false    | none        | User ID                                | ID of the owning user.                                                         |
| accountId               | string(int64) | false    | none        | Account ID                             | ID of the owning account.                                                        |
| coinId                  | string(int64) | false    | none        | Collateral Coin ID                     | ID of the associated collateral coin.                                             |
| contractId              | string(int64) | false    | none        | Contract ID                             | ID of the associated contract.                                                  |
| positionValue           | string        | false    | none        | Position Value                         | Position value, positive for long positions, negative for short positions.         |
| maxLeverage             | string        | false    | none        | Maximum Leverage                      | The maximum leverage for current contract position.                              |
| initialMarginRequirement| string        | false    | none        | Initial Margin Requirement            | Initial margin requirement for the position.                                   |
| starkExRiskRate         | string        |false    | none        | StarkEx Risk Rate                      | StarkEx risk rate calculated based on risk tiers. Similar to maintenance margin rate with different precision. |
| starkExRiskValue        | string        | false    | none        | StarkEx Risk Value                   | StarkEx risk amount, similar to maintenance margin, with different precision.     |
| avgEntryPrice           | string        | false    | none        | Average Entry Price                   | Average entry price.                                                            |
| liquidatePrice          | string        | false    | none        | Liquidation Price                     | Liquidation price (force liquidation price). If oracle price reaches this price, liquidation is triggered.        |
| bankruptPrice           | string        | false    | none        | Bankruptcy Price                      | Bankruptcy price. If the oracle price reaches this level, account total value is less than 0.     |
| worstClosePrice         | string        | false    | none        | Worst Close Price                     | The worst closing price. The closing transaction price can not be worse than this price. |
| unrealizePnl            | string        | false    | none        | Unrealized PnL                         | Unrealized profit and loss for the position.                                     |
| termRealizePnl          | string        | false    | none        | Term Realized PnL                    | Realized PnL for the term.                                            |
| totalRealizePnl        | string        | false    | none        | Total Realized PnL                   | Total realized PnL of the position.                                         |

<h2 id="tocS_Position">Position</h2>

<a id="schemaposition"></a>
<a id="schema_Position"></a>
<a id="tocSposition"></a>
<a id="tocsposition"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "openSize": "string",
  "openValue": "string",
  "openFee": "string",
  "fundingFee": "string",
  "longTermCount": 0,
  "longTermStat": {
    "cumOpenSize": "string",
    "cumOpenValue": "string",
    "cumOpenFee": "string",
    "cumCloseSize": "string",
    "cumCloseValue": "string",
    "cumCloseFee": "string",
    "cumFundingFee": "string",
    "cumLiquidateFee": "string"
  },
  "longTermCreatedTime": "string",
  "longTermUpdatedTime": "string",
  "shortTermCount": 0,
  "shortTermStat": {
    "cumOpenSize": "string",
    "cumOpenValue": "string",
    "cumOpenFee": "string",
    "cumCloseSize": "string",
    "cumCloseValue": "string",
    "cumCloseFee": "string",
    "cumFundingFee": "string",
    "cumLiquidateFee": "string"
  },
  "shortTermCreatedTime": "string",
  "shortTermUpdatedTime": "string",
  "longTotalStat": {
    "cumOpenSize": "string",
    "cumOpenValue": "string",
    "cumOpenFee": "string",
    "cumCloseSize": "string",
    "cumCloseValue": "string",
    "cumCloseFee": "string",
    "cumFundingFee": "string",
    "cumLiquidateFee": "string"
  },
  "shortTotalStat": {
    "cumOpenSize": "string",
    "cumOpenValue": "string",
    "cumOpenFee": "string",
    "cumCloseSize": "string",
    "cumCloseValue": "string",
    "cumCloseFee": "string",
    "cumFundingFee": "string",
    "cumLiquidateFee": "string"
  },
  "createdTime": "string",
  "updatedTime": "string"
}
```

Perpetual contract position information

### Properties

| Name                | Type          | Required | Constraints | Description                                                         | Notes                                                                                      |
| ------------------- | ------------- | -------- | ----------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| userId              | string(int64) | false    | none        | User ID                                                             | ID of the owning user.                                                                     |
| accountId           | string(int64) | false    | none        | Account ID                                                          | ID of the owning account.                                                                |
| coinId              | string(int64) | false    | none        | Collateral Coin ID                                                  | ID of the associated collateral coin.                                                       |
| contractId          | string(int64) | false    | none        | Contract ID                                                          | ID of the associated contract.                                                              |
| openSize            | string        | false    | none        | Current Open Size                                                   | Current open size (positive for long, negative for short).                                   |
| openValue           | string        | false    | none        | Current Open Value                                                  | Current open value (increases upon opening, proportionally decreases upon closing).        |
| openFee             | string        | false    | none        | Current Open Fee                                                     | Current allocated open fee (increases upon opening, proportionally decreases upon closing). |
| fundingFee          | string        | false    | none        | Current Funding Fee                                                  | Current allocated funding fee (increases upon settlement, proportionally decreases upon closing). |
| longTermCount       | integer(int32) | false    | none        | Long Position Term Count                                            | Long position term count. Starts from 1, increases by one upon complete closure of a position |
| longTermStat        | [PositionStat](#schemapositionstat) | false    | none        | Long Position Cumulative Statistics | Cumulative statistics for the position.                                              |
| longTermCreatedTime | string        | false    | none        | Long Position Term Creation Time                                            | Creation time for the long position term.                                                 |
| longTermUpdatedTime | string        | false    | none        | Long Position Term Update Time                                            | Update time for the long position term.                                                  |
| shortTermCount      | integer(int32) | false    | none        | Short Position Term Count                                           | Short position term count. Starts from 1, increases by one upon complete closure of a position|
| shortTermStat        | [PositionStat](#schemapositionstat) | false    | none        | Short Position Cumulative Statistics| Cumulative statistics for the position.                                              |
| shortTermCreatedTime| string        | false    | none        | Short Position Term Creation Time                                           | Creation time for the short position term.                                                |
| shortTermUpdatedTime| string        | false    | none        | Short Position Term Update Time                                           | Update time for the short position term.                                                |
| longTotalStat       | [PositionStat](#schemapositionstat) | false    | none        | Long Cumulative Statistics                | Cumulative statistics for the position.                                              |
| shortTotalStat      | [PositionStat](#schemapositionstat) | false    | none        | Short Cumulative Statistics                | Cumulative statistics for the position.                                              |
| createdTime         | string(int64) | false    | none        | Creation Time                                                         | Creation time.                                                                             |
| updatedTime         | string(int64) | false    | none        | Update Time                                                        | Update time.                                                                            |

<h2 id="tocS_PositionStat">PositionStat</h2>

<a id="schemapositionstat"></a>
<a id="schema_PositionStat"></a>
<a id="tocSpositionstat"></a>
<a id="tocspositionstat"></a>

```json
{
  "cumOpenSize": "string",
  "cumOpenValue": "string",
  "cumOpenFee": "string",
  "cumCloseSize": "string",
  "cumCloseValue": "string",
  "cumCloseFee": "string",
  "cumFundingFee": "string",
  "cumLiquidateFee": "string"
}
```

Cumulative statistics for a position

### Properties

| Name            | Type   | Required | Constraints | Description              | Notes                                                               |
| --------------- | ------ | -------- | ----------- | ------------------------ | ------------------------------------------------------------------- |
| cumOpenSize     | string | false    | none        | Cumulative Open Size     | Cumulative open size.                                               |
| cumOpenValue    | string | false    | none        | Cumulative Open Value   | Cumulative open value.                                              |
| cumOpenFee      | string | false    | none        | Cumulative Open Fee     | Cumulative open fees.                                               |
| cumCloseSize    | string | false    | none        | Cumulative Close Size   | Cumulative close size.                                              |
| cumCloseValue   | string | false    | none        | Cumulative Close Value  | Cumulative close value.                                             |
| cumCloseFee     | string | false    | none        | Cumulative Close Fee    | Cumulative close fees.                                              |
| cumFundingFee   | string | false    | none        | Cumulative Funding Fee  | Cumulative funding fees settled.                                      |
| cumLiquidateFee | string | false    | none        | Cumulative Liquidate Fee| Cumulative liquidation fees.                                          |

<h2 id="tocS_Collateral">Collateral</h2>

<a id="schemacollateral"></a>
<a id="schema_Collateral"></a>
<a id="tocScollateral"></a>
<a id="tocscollateral"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "legacyAmount": "string",
  "cumDepositAmount": "string",
  "cumWithdrawAmount": "string",
  "cumTransferInAmount": "string",
  "cumTransferOutAmount": "string",
  "cumPositionBuyAmount": "string",
  "cumPositionSellAmount": "string",
  "cumFillFeeAmount": "string",
  "cumFundingFeeAmount": "string",
  "cumFillFeeIncomeAmount": "string",
  "createdTime": "string",
  "updatedTime": "string"
}
```

Collateral information

### Properties

| Name                  | Type            | Required | Constraints | Description                                   | Notes                                                                    |
| --------------------- | --------------- | -------- | ----------- | --------------------------------------------- | ------------------------------------------------------------------------ |
| userId                | string(int64)   | false    | none        | User ID                                       | ID of the owning user.                                                  |
| accountId             | string(int64)   | false    | none        | Account ID                                    | ID of the owning account.                                                 |
| coinId                | string(int64)   | false    | none        | Coin ID                                       | Collateral coin ID.                                                       |
| amount                | string(decimal) | false    | none        | Collateral Amount                             | Collateral amount, actually of decimal type.                               |
| legacyAmount          | string(decimal) | false    | none        | Legacy Amount                                 | Legacy balance field, for display purposes only, not for calculations.   |
| cumDepositAmount      | string(decimal) | false    | none        | Cumulative Deposit Amount                     | Cumulative deposit amount.                                               |
| cumWithdrawAmount     | string(decimal) | false    | none        | Cumulative Withdrawal Amount                  | Cumulative withdrawal amount.                                             |
| cumTransferInAmount   | string(decimal) | false    | none        | Cumulative Transfer In Amount                  | Cumulative transfer in amount.                                              |
| cumTransferOutAmount  | string(decimal) | false    | none        | Cumulative Transfer Out Amount                 | Cumulative transfer out amount.                                             |
| cumPositionBuyAmount  | string(decimal) | false    | none        | Cumulative Position Buy Amount                | Cumulative collateral amount deducted from position buy.                     |
| cumPositionSellAmount | string(decimal) | false    | none        | Cumulative Position Sell Amount                | Cumulative collateral amount added from position sell.                    |
| cumFillFeeAmount      | string(decimal) | false    | none        | Cumulative Fill Fee Amount                    | Cumulative transaction fee amount.                                            |
| cumFundingFeeAmount   | string(decimal) | false    | none        | Cumulative Funding Fee Amount                 | Cumulative funding fee amount.                                              |
| cumFillFeeIncomeAmount| string(decimal) | false    | none        | Cumulative Order Fill Fee Income Amount       | Cumulative amount from order fill fee income.                                 |
| createdTime           | string(int64)   | false    | none        | Creation Time                                 | Creation time.                                                               |
| updatedTime           | string(int64)   | false    | none        | Update Time                                    | Update time.                                                                  |

<h2 id="tocS_Account">Account</h2>

<a id="schemaaccount"></a>
<a id="schema_Account"></a>
<a id="tocSaccount"></a>
<a id="tocsaccount"></a>

```json
{
  "id": "string",
  "userId": "string",
  "ethAddress": "string",
  "l2Key": "string",
  "l2KeyYCoordinate": "string",
  "clientAccountId": "string",
  "isSystemAccount": true,
  "defaultTradeSetting": {
    "isSetFeeRate": true,
    "takerFeeRate": "string",
    "makerFeeRate": "string",
    "isSetFeeDiscount": true,
    "takerFeeDiscount": "string",
    "makerFeeDiscount": "string",
    "isSetMaxLeverage": true,
    "maxLeverage": "string"
  },
  "contractIdToTradeSetting": {
    "property1": {
      "isSetFeeRate": true,
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "isSetFeeDiscount": true,
      "takerFeeDiscount": "string",
      "makerFeeDiscount": "string",
      "isSetMaxLeverage": true,
      "maxLeverage": "string"
    },
    "property2": {
      "isSetFeeRate": true,
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "isSetFeeDiscount": true,
      "takerFeeDiscount": "string",
      "makerFeeDiscount": "string",
      "isSetMaxLeverage": true,
      "maxLeverage": "string"
    }
  },
  "maxLeverageLimit": "string",
  "createOrderPerMinuteLimit": 0,
  "createOrderDelayMillis": 0,
  "extraType": "string",
  "extraDataJson": "string",
  "status": "UNKNOWN_ACCOUNT_STATUS",
  "isLiquidating": true,
  "createdTime": "string",
  "updatedTime": "string"
}
```

Account information data.

### Properties

| Name                    | Type                | Required | Constraints | Description                                                                                                                                  | Notes                                                                                     |
| ----------------------- | ------------------- | -------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| id                      | string(int64)       | false    | none        | Account ID                                                                                                                                 | Account ID, must be greater than 0.                                                      |
| userId                  | string(int64)       | false    | none        | User ID                                                                                                                                    | ID of the owning user.                                                                    |
| ethAddress              | string              | false    | none        | Wallet ETH Address                                                                                                                          | Wallet ETH address.                                                                      |
| l2Key                   | string              | false    | none        | L2 Account Key                                                                                                                              | Account key on L2. Stark key in starkEx. Bigint for hex string                             |
| l2KeyYCoordinate        | string              | false    | none        | L2 Key Y Coordinate                                                                                                                        | Used only for verifying l2Signature. Not returned to end users. Bigint for hex string.    |
| clientAccountId         | string              | false    | none        | Client Account ID                                                                                                                            | Client account ID for idempotency check.                                                   |
| isSystemAccount         | boolean             | false    | none        | System Account                                                                                                                             | Whether it is a system account (system accounts are not subject to contract risk settings, use separate MQ for trade messages). |
| defaultTradeSetting     | [TradeSetting](#schematradesetting) | false    | none        | Default Trade Setting                                                                                                    | Trade settings. Trade setting calculation priority: Account contract trade settings -> Account default trade settings -> Contract configuration trade settings. Note: Only one of `is_set_fee_rate` and `is_set_fee_discount` can be true.                                     |
| contractIdToTradeSetting| object              | false    | none        | Contract-Level Account Trade Settings                                                                                                    | Account contract-level trade settings.                                                     |
| » **additionalProperties**| [TradeSetting](#schematradesetting) | false    | none        | Contract-Level Account Trade Settings                                                                                                    | Trade settings. Trade setting calculation priority: Account contract trade settings -> Account default trade settings -> Contract configuration trade settings. Note: Only one of `is_set_fee_rate` and `is_set_fee_discount` can be true.                                                     |
| maxLeverageLimit        | string              | false    | none        | Maximum Leverage Limit                                                                                                                       | User-set maximum leverage limit. If 0, uses the leverage limit of the corresponding trading contract.  |
| createOrderPerMinuteLimit| integer(int32)     | false    | none        | Order Creation Limit per Minute                                                                                                        | Order frequency limit per minute. If 0, default limit is used; if < 0, no limit is applied. |
| createOrderDelayMillis  | integer(int32)     | false    | none        | Order Creation Delay Milliseconds                                                                                                        | Order delay milliseconds, must be greater than or equal to 0.                         |
| extraType               | string              | false    | none        | Extra Type                                                                                                                                 | Extra type for upper-layer use.                                                            |
| extraDataJson           | string              | false    | none        | Extra Data                                                                                                                               | Extra data in JSON format, default is an empty string.                                     |
| status                  | string              | false    | none        | Account Status                                                                                                                            | Account status.                                                                           |
| isLiquidating           | boolean             | false    | none        | Is Liquidating                                                                                                                            | Whether is being liquidated.                                                              |
| createdTime             | string(int64)       | false    | none        | Creation Time                                                                                                                              | Creation time.                                                                            |
| updatedTime             | string(int64)       | false    | none        | Update Time                                                                                                                                 | Update time.                                                                               |

#### Enumerated Values

| Property | Value                 |
| -------- | --------------------- |
| status   | UNKNOWN_ACCOUNT_STATUS |
| status   | CENSORING             |
| status   | NORMAL                |
| status   | DISABLED              |
| status   | INVALID               |
| status   | UNRECOGNIZED          |

<h2 id="tocS_TradeSetting">TradeSetting</h2>

<a id="schematradesetting"></a>
<a id="schema_TradeSetting"></a>
<a id="tocStradesetting"></a>
<a id="tocstradesetting"></a>

```json
{
  "isSetFeeRate": true,
  "takerFeeRate": "string",
  "makerFeeRate": "string",
  "isSetFeeDiscount": true,
  "takerFeeDiscount": "string",
  "makerFeeDiscount": "string",
  "isSetMaxLeverage": true,
  "maxLeverage": "string"
}
```

Trade settings. Trade setting calculation priority: Account contract trade settings -> Account default trade settings -> Contract configuration trade settings. Note: Only one of `is_set_fee_rate` and `is_set_fee_discount` can be true.

### Properties

| Name              | Type            | Required | Constraints | Description                                                                                    | Notes                                                                                          |
| ----------------- | --------------- | -------- | ----------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| isSetFeeRate      | boolean         | false    | none        | Whether Fee Rate is Set                                                                        | Whether to set a specific fee rate value.                                                        |
| takerFeeRate      | string(decimal) | false    | none        | Taker Fee Rate                                                                                 | Taker fee rate, range [0, 1), valid only when is_set_fee_rate=true.                                    |
| makerFeeRate      | string(decimal) | false    | none        | Maker Fee Rate                                                                                 | Maker fee rate, range [0, 1), valid only when is_set_fee_rate=true.                                     |
| isSetFeeDiscount  | boolean         | false    | none        | Whether Fee Discount is Set                                                                  | Whether to set a fee discount.                                                                   |
| takerFeeDiscount  | string(decimal) | false    | none        | Taker Fee Discount                                                                             | Taker fee discount, range [0, 1), valid only when is_set_fee_discount=true.                      |
| makerFeeDiscount  | string(decimal) | false    | none        | Maker Fee Discount                                                                             | Maker fee discount, range [0, 1), valid only when is_set_fee_discount=true.                       |
| isSetMaxLeverage  | boolean         | false    | none        | Whether Maximum Leverage is Set                                                                  | Whether to set maximum trading leverage.                                                      |
| maxLeverage       | string(decimal) | false    | none        | Maximum Leverage                                                                             | Maximum trading leverage.                                                                          |

<h2 id="tocS_Result<Account>">Result&lt;Account&gt;</h2>

<a id="schemaresult<account>"></a>
<a id="schema_Result<Account>"></a>
<a id="tocSresult<account>"></a>
<a id="tocsresult<account>"></a>

```json
{
  "code": "string",
  "data": {
    "id": "string",
    "userId": "string",
    "ethAddress": "string",
    "l2Key": "string",
    "l2KeyYCoordinate": "string",
    "clientAccountId": "string",
    "isSystemAccount": true,
    "defaultTradeSetting": {
      "isSetFeeRate": true,
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "isSetFeeDiscount": true,
      "takerFeeDiscount": "string",
      "makerFeeDiscount": "string",
      "isSetMaxLeverage": true,
      "maxLeverage": "string"
    },
    "contractIdToTradeSetting": {
      "property1": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      },
      "property2": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      }
    },
    "maxLeverageLimit": "string",
    "createOrderPerMinuteLimit": 0,
    "createOrderDelayMillis": 0,
    "extraType": "string",
    "extraDataJson": "string",
    "status": "UNKNOWN_ACCOUNT_STATUS",
    "isLiquidating": true,
    "createdTime": "string",
    "updatedTime": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                                 | Required | Constraints | Description                | Notes                                                                    |
| -------------- | ------------------------------------ | -------- | ----------- | -------------------------- | ------------------------------------------------------------------------ |
| code           | string                               | false    | none        | Status Code                | Returns "SUCCESS" on success; otherwise, it indicates failure.            |
| data           | [Account](#schemaaccount)            | false    | none        | Account Information      | Account information data.                                                 |
| errorParam     | object                               | false    | none        | Error Parameters           | Error message parameter information                                       |
| » **additionalProperties** | string                               | false    | none        | Error Parameters           | Error message parameter information                                       |
| requestTime    | string(timestamp)                    | false    | none        | Server Request Time       | Time at which the server received the request                             |
| responseTime   | string(timestamp)                    | false    | none        | Server Response Time      | Time at which the server sent the response                                |
| traceId        | string                               | false    | none        | Trace ID                  | Invocation trace ID                                                     |

<h2 id="tocS_Result<GetAccountDeleverageLight>">Result&lt;GetAccountDeleverageLight&gt;</h2>

<a id="schemaresult<getaccountdeleveragelight>"></a>
<a id="schema_Result<GetAccountDeleverageLight>"></a>
<a id="tocSresult<getaccountdeleveragelight>"></a>
<a id="tocsresult<getaccountdeleveragelight>"></a>

```json
{
  "code": "string",
  "data": {
    "positionContractIdToLightNumberMap": {
      "property1": 0,
      "property2": 0
    }
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                                   | Required | Constraints | Description                        | Notes                                                                  |
| -------------- | -------------------------------------- | -------- | ----------- | ---------------------------------- | ---------------------------------------------------------------------- |
| code           | string                                 | false    | none        | Status Code                        | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [GetAccountDeleverageLight](#schemagetaccountdeleveragelight) | false    | none        | Get Account Deleverage Light Response  | Response structure for fetching deleverage light information.         |
| errorParam     | object                                 | false    | none        | Error Parameters                   | Error message parameter information                                     |
| » **additionalProperties** | string                                 | false    | none        | Error Parameters                   | Error message parameter information                                     |
| requestTime    | string(timestamp)                      | false    | none        | Server Request Time               | Time at which the server received the request                           |
| responseTime   | string(timestamp)                      | false    | none        | Server Response Time              | Time at which the server sent the response                              |
| traceId        | string                                 | false    | none        | Trace ID                          | Invocation trace ID                                                  |

<h2 id="tocS_GetAccountDeleverageLight">GetAccountDeleverageLight</h2>

<a id="schemagetaccountdeleveragelight"></a>
<a id="schema_GetAccountDeleverageLight"></a>
<a id="tocSgetaccountdeleveragelight"></a>
<a id="tocsgetaccountdeleveragelight"></a>

```json
{
  "positionContractIdToLightNumberMap": {
    "property1": 0,
    "property2": 0
  }
}
```

Response structure for fetching deleverage light information.

### Properties

| Name                         | Type   | Required | Constraints | Description                                                                          | Notes                                                                         |
| ---------------------------- | ------ | -------- | ----------- | ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
| positionContractIdToLightNumberMap | object | false    | none        | Map from Position Contract ID to Light Number                                   | Maps position contract ID to light number. `light_number` ranges from 1-5, which represent 1-5 lights. |
| » **additionalProperties**           | integer(int32) | false    | none        | Map from Position Contract ID to Light Number  | Maps position contract ID to light number. `light_number` ranges from 1-5, which represent 1-5 lights. |

<h2 id="tocS_Result<PageData<Account>>">Result&lt;PageData&lt;Account&gt;&gt;</h2>

<a id="schemaresult<pagedata<account>>"></a>
<a id="schema_Result<PageData<Account>>"></a>
<a id="tocSresult<pagedata<account>>"></a>
<a id="tocsresult<pagedata<account>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "ethAddress": "string",
        "l2Key": "string",
        "l2KeyYCoordinate": "string",
        "clientAccountId": "string",
        "isSystemAccount": true,
        "defaultTradeSetting": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        },
        "contractIdToTradeSetting": {
          "property1": {
            "isSetFeeRate": null,
            "takerFeeRate": null,
            "makerFeeRate": null,
            "isSetFeeDiscount": null,
            "takerFeeDiscount": null,
            "makerFeeDiscount": null,
            "isSetMaxLeverage": null,
            "maxLeverage": null
          },
          "property2": {
            "isSetFeeRate": null,
            "takerFeeRate": null,
            "makerFeeRate": null,
            "isSetFeeDiscount": null,
            "takerFeeDiscount": null,
            "makerFeeDiscount": null,
            "isSetMaxLeverage": null,
            "maxLeverage": null
          }
        },
        "maxLeverageLimit": "string",
        "createOrderPerMinuteLimit": 0,
        "createOrderDelayMillis": 0,
        "extraType": "string",
        "extraDataJson": "string",
        "status": "UNKNOWN_ACCOUNT_STATUS",
        "isLiquidating": true,
        "createdTime": "string",
        "updatedTime": "string"
      }
    ],
    "nextPageOffsetData": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                               | Required | Constraints | Description              | Notes                                                                    |
| -------------- | ---------------------------------- | -------- | ----------- | ------------------------ | ------------------------------------------------------------------------ |
| code           | string                             | false    | none        | Status Code              | Returns "SUCCESS" on success; otherwise, it indicates failure.            |
| data           | [PageDataAccount](#schemapagedataaccount)   | false    | none        | Generic Paginated Response | Generic paginated response.                                                                     |
| errorParam     | object                             | false    | none        | Error Parameters         | Error message parameter information                                       |
| » **additionalProperties** | string                               | false    | none        | Error Parameters         | Error message parameter information                                       |
| requestTime    | string(timestamp)                  | false    | none        | Server Request Time     | Time at which the server received the request                             |
| responseTime   | string(timestamp)                  | false    | none        | Server Response Time    | Time at which the server sent the response                                |
| traceId        | string                             | false    | none        | Trace ID                | Invocation trace ID                                                  |

<h2 id="tocS_PageDataAccount">PageDataAccount</h2>

<a id="schemapagedataaccount"></a>
<a id="schema_PageDataAccount"></a>
<a id="tocSpagedataaccount"></a>
<a id="tocspagedataaccount"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "ethAddress": "string",
      "l2Key": "string",
      "l2KeyYCoordinate": "string",
      "clientAccountId": "string",
      "isSystemAccount": true,
      "defaultTradeSetting": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      },
      "contractIdToTradeSetting": {
        "property1": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        },
        "property2": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        }
      },
      "maxLeverageLimit": "string",
      "createOrderPerMinuteLimit": 0,
      "createOrderDelayMillis": 0,
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ACCOUNT_STATUS",
      "isLiquidating": true,
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "nextPageOffsetData": "string"
}
```

Generic Paginated Response

### Properties

| Name               | Type                     | Required | Constraints | Description                 | Notes                                                               |
| ------------------ | ------------------------ | -------- | ----------- | --------------------------- | ------------------------------------------------------------------- |
| dataList           | [[Account](#schemaaccount)]       | false    | none        | Data List                  | List of account data.                                                               |
| nextPageOffsetData | string                   | false    | none        | Next Page Offset        | Offset for retrieving the next page. If no next page data, empty string. |

<h2 id="tocS_Result<List<Collateral>>">Result&lt;List&lt;Collateral&gt;&gt;</h2>

<a id="schemaresult<list<collateral>>"></a>
<a id="schema_Result<List<Collateral>>"></a>
<a id="tocSresult<list<collateral>>"></a>
<a id="tocsresult<list<collateral>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "amount": "string",
      "legacyAmount": "string",
      "cumDepositAmount": "string",
      "cumWithdrawAmount": "string",
      "cumTransferInAmount": "string",
      "cumTransferOutAmount": "string",
      "cumPositionBuyAmount": "string",
      "cumPositionSellAmount": "string",
      "cumFillFeeAmount": "string",
      "cumFundingFeeAmount": "string",
      "cumFillFeeIncomeAmount": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                      | Required | Constraints | Description        | Notes                                                                  |
| -------------- | ------------------------- | -------- | ----------- | ------------------ | ---------------------------------------------------------------------- |
| code           | string                    | false    | none        | Status Code        | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [[Collateral](#schemacollateral)] | false    | none        | Response Data     | Correct response data.                                                  |
| errorParam     | object                    | false    | none        | Error Parameters   | Error message parameter information                                     |
| » **additionalProperties** | string                    | false    | none        | Error Parameters   | Error message parameter information                                     |
| requestTime    | string(timestamp)         | false    | none        | Server Request Time | Time at which the server received the request                           |
| responseTime   | string(timestamp)         | false    | none        | Server Response Time| Time at which the server sent the response                              |
| traceId        | string                    | false    | none        | Trace ID           | Invocation trace ID                                                  |

<h2 id="tocS_Result<List<CollateralTransaction>>">Result&lt;List&lt;CollateralTransaction&gt;&gt;</h2>

<a id="schemaresult<list<collateraltransaction>>"></a>
<a id="schema_Result<List<CollateralTransaction>>"></a>
<a id="tocSresult<list<collateraltransaction>>"></a>
<a id="tocsresult<list<collateraltransaction>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
      "deltaAmount": "string",
      "deltaLegacyAmount": "string",
      "beforeAmount": "string",
      "beforeLegacyAmount": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "depositId": "string",
      "withdrawId": "string",
      "transferInId": "string",
      "transferOutId": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "orderAccountId": "string",
      "positionContractId": "string",
      "positionTransactionId": "string",
      "forceWithdrawId": "string",
      "forceTradeId": "string",
      "extraType": "string",
      "extraDataJson": "string",
      "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2RejectTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l2ApprovedTime": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                            | Required | Constraints | Description        | Notes                                                                  |
| -------------- | ------------------------------- | -------- | ----------- | ------------------ | ---------------------------------------------------------------------- |
| code           | string                          | false    | none        | Status Code        | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [[CollateralTransaction](#schemacollateraltransaction)] | false    | none        | Response Data     | Correct response data.                                                  |
| errorParam     | object                          | false    | none        | Error Parameters   | Error message parameter information                                     |
| » **additionalProperties** | string                          | false    | none        | Error Parameters   | Error message parameter information                                     |
| requestTime    | string(timestamp)               | false    | none        | Server Request Time | Time at which the server received the request                           |
| responseTime   | string(timestamp)               | false    | none        | Server Response Time| Time at which the server sent the response                              |
| traceId        | string                          | false    | none        | Trace ID           | Invocation trace ID                                                  |

<h2 id="tocS_CollateralTransaction">CollateralTransaction</h2>

<a id="schemacollateraltransaction"></a>
<a id="schema_CollateralTransaction"></a>
<a id="tocScollateraltransaction"></a>
<a id="tocscollateraltransaction"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
  "deltaAmount": "string",
  "deltaLegacyAmount": "string",
  "beforeAmount": "string",
  "beforeLegacyAmount": "string",
  "fillCloseSize": "string",
  "fillCloseValue": "string",
  "fillCloseFee": "string",
  "fillOpenSize": "string",
  "fillOpenValue": "string",
  "fillOpenFee": "string",
  "fillPrice": "string",
  "liquidateFee": "string",
  "realizePnl": "string",
  "isLiquidate": true,
  "isDeleverage": true,
  "fundingTime": "string",
  "fundingRate": "string",
  "fundingIndexPrice": "string",
  "fundingOraclePrice": "string",
  "fundingPositionSize": "string",
  "depositId": "string",
  "withdrawId": "string",
  "transferInId": "string",
  "transferOutId": "string",
  "transferReason": "UNKNOWN_TRANSFER_REASON",
  "orderId": "string",
  "orderFillTransactionId": "string",
  "orderAccountId": "string",
  "positionContractId": "string",
  "positionTransactionId": "string",
  "forceWithdrawId": "string",
  "forceTradeId": "string",
  "extraType": "string",
  "extraDataJson": "string",
  "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
  "censorTxId": "string",
  "censorTime": "string",
  "censorFailCode": "string",
  "censorFailReason": "string",
  "l2TxId": "string",
  "l2RejectTime": "string",
  "l2RejectCode": "string",
  "l2RejectReason": "string",
  "l2ApprovedTime": "string",
  "createdTime": "string",
  "updatedTime": "string"
}
```

Collateral transaction details.

### Properties

| Name                    | Type            | Required | Constraints | Description                                                                                    | Notes                                                                                             |
| ----------------------- | --------------- | -------- | ----------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| id                      | string(int64)   | false    | none        | Unique Identifier                                                                              | Unique identifier.                                                                                |
| userId                  | string(int64)   | false    | none        | User ID                                                                                        | ID of the owning user.                                                                           |
| accountId               | string(int64)   | false    | none        | Account ID                                                                                     | ID of the owning account.                                                                       |
| coinId                  | string(int64)   | false    | none        | Coin ID                                                                                        | Collateral coin ID.                                                                             |
| type                    | string          | false    | none        | Detail Type                                                                                    | Detail type.                                                                                      |
| deltaAmount             | string(decimal) | false    | none        | Collateral Change Amount                                                                       | Amount of the collateral change.                                                                |
| deltaLegacyAmount       | string(decimal) | false    | none        | Legacy Balance Change Amount                                                                   | Change amount of the legacy balance field.                                                    |
| beforeAmount            | string(decimal) | false    | none        | Collateral Amount Before Change                                                                | Collateral amount before the change.                                                             |
| beforeLegacyAmount      | string(decimal) | false    | none        | Legacy Balance Amount Before Change                                                            | Legacy balance before the change.                                                                  |
| fillCloseSize           | string(decimal) | false    | none        | Transaction Close Size                                                                       | Transaction close size (positive for buy, negative for sell).                                          |
| fillCloseValue          | string          | false    | none        | Transaction Close Value                                                                       | Transaction close value (positive for buy, negative for sell).                                     |
| fillCloseFee            | string          | false    | none        | Transaction Close Fee                                                                          | Transaction close fee (typically zero or negative).                                             |
| fillOpenSize            | string(decimal) | false    | none        | Transaction Open Size                                                                        | Transaction open size (positive for buy, negative for sell).                                          |
| fillOpenValue           | string          | false    | none        | Transaction Open Value                                                                        | Transaction open value (positive for buy, negative for sell).                                     |
| fillOpenFee             | string          | false    | none        | Transaction Open Fee                                                                           | Transaction open fee (typically zero or negative).                                             |
| fillPrice               | string(decimal) | false    | none        | Transaction Price                                                                              | Transaction price (not precise, for display).                                              |
| liquidateFee            | string(decimal) | false    | none        | Liquidation Fee                                                                                | Liquidation fee (if close transaction is a liquidation, typically zero or negative).            |
| realizePnl              | string(decimal) | false    | none        | Realized Profit and Loss                                                                        | Realized profit and loss from a close (if a close transaction. Not precise, for display). |
| isLiquidate             | boolean         | false    | none        | Is Liquidation                                                                                   | Whether the transaction is a liquidation.                                                      |
| isDeleverage            | boolean         | false    | none        | Is Auto-Deleveraging                                                                         | Whether the transaction is from auto-deleveraging.                                            |
| fundingTime             | string(int64)   | false    | none        | Funding Settlement Time                                                                      | Funding settlement time.                                                                        |
| fundingRate             | string(decimal) | false    | none        | Funding Rate                                                                                    | Funding rate.                                                                                    |
| fundingIndexPrice       | string(decimal) | false    | none        | Funding Index Price                                                                           | Index price related to funding rate.                                                         |
| fundingOraclePrice      | string(decimal) | false    | none        | Funding Oracle Price                                                                          | Oracle price related to funding rate.                                                        |
| fundingPositionSize     | string(decimal) | false    | none        | Position Size During Funding Settlement                                                      | Position size during funding settlement (positive for long, negative for short).             |
| depositId               | string(int64)   | false    | none        | Deposit Order ID                                                                               | Associated deposit order ID when type=DEPOSIT.                                                 |
| withdrawId              | string(int64)   | false    | none        | Withdrawal Order ID                                                                            | Associated withdrawal order ID when type=WITHDRAW.                                              |
| transferInId            | string(int64)   | false    | none        | Transfer In Order ID                                                                           | Associated transfer-in order ID when type=TRANSFER_IN.                                           |
| transferOutId           | string(int64)   | false    | none        | Transfer Out Order ID                                                                          | Associated transfer-out order ID when type=TRANSFER_OUT.                                          |
| transferReason          | string          | false    | none        | Transfer Reason                                                                               | Transfer reason when type=TRANSFER_IN/TRANSFER_OUT.                                         |
| orderId                 | string(int64)   | false    | none        | Order ID                                                                                       | Associated order ID when type=POSITION_BUY/POSITION_SELL/FILL_FEE_INCOME.                      |
| orderFillTransactionId  | string(int64)   | false    | none        | Order Fill Transaction ID                                                                    | Associated order fill transaction ID when type=POSITION_BUY/POSITION_SELL/FILL_FEE_INCOME.   |
| orderAccountId          | string(int64)   | false    | none        | Order Account ID                                                                             | Associated order account ID when type=FILL_FEE_INCOME.                                         |
| positionContractId      | string(int64)   | false    | none        | Position Contract ID                                                                           | Associated position contract ID when type=POSITION_BUY/POSITION_SELL/POSITION_FUNDING/FILL_FEE_INCOME. |
| positionTransactionId  | string(int64)   | false    | none        | Position Transaction ID                                                                    | Associated position transaction ID when type=POSITION_BUY/POSITION_SELL/POSITION_FUNDING.     |
| forceWithdrawId         | string          | false    | none        | Force Withdrawal Order ID                                                                      | Associated force withdrawal order ID when type=WITHDRAW.                                    |
| forceTradeId            | string          | false    | none        | Force Trade ID                                                                                 | Associated force trade order ID when type=POSITION_BUY/POSITION_SELL.                           |
| extraType               | string          | false    | none        | Extra Type                                                                                     | Extra type for upper-layer business use.                                                     |
| extraDataJson           | string          | false    | none        | Extra Data                                                                                    | Extra data in JSON format, default is empty string.                                          |
| censorStatus            | string          | false    | none        | Current Censoring Status                                                                       | Current censoring status.                                                                     |
| censorTxId              | string(int64)   | false    | none        | Censoring Processing Sequence Number                                                       | Censoring processing sequence number, exists when censor_status=CENSOR_SUCCESS/CENSOR_FAILURE/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED.   |
| censorTime              | string(int64)   | false    | none        | Censoring Processing Time                                                                    | Censoring processing time, exists when censor_status=CENSOR_SUCCESS/CENSOR_FAILURE/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED.   |
| censorFailCode          | string          | false    | none        | Censoring Failure Code                                                                         | Censoring failure code, exists when censor_status=CENSOR_FAILURE.                           |
| censorFailReason        | string          | false    | none        | Censoring Failure Reason                                                                       | Censoring failure reason, exists when censor_status=CENSOR_FAILURE.                         |
| l2TxId                  | string(int64)   | false    | none        | L2 Push Transaction ID                                                                          | L2 push transaction ID, exists when censor_status=CENSOR_SUCCESS/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED.    |
| l2RejectTime            | string(int64)   | false    | none        | L2 Rejection Time                                                                             | L2 rejection time, exists when censor_status=L2_REJECT/L2_REJECT_APPROVED.                 |
| l2RejectCode            | string          | false    | none        | L2 Rejection Error Code                                                                        | L2 rejection error code, exists when censor_status=L2_REJECT/L2_REJECT_APPROVED.             |
| l2RejectReason          | string          | false    | none        | L2 Rejection Reason                                                                          | L2 rejection reason, exists when censor_status=L2_REJECT/L2_REJECT_APPROVED.             |
| l2ApprovedTime          | string(int64)   | false    | none        | L2 Batch Verification Time                                                                   | L2 batch verification time, exists when censor_status=L2_APPROVED/L2_REJECT_APPROVED.         |
| createdTime             | string(int64)   | false    | none        | Creation Time                                                                                  | Creation time.                                                                              |
| updatedTime             | string(int64)   | false    | none        | Update Time                                                                                   | Update time.                                                                                 |

#### Enumerated Values

| Property       | Value                            |
| -------------- | -------------------------------- |
| type           | UNKNOWN_COLLATERAL_TRANSACTION_TYPE    |
| type           | DEPOSIT                       |
| type           | WITHDRAW                      |
| type           | TRANSFER_IN                   |
| type           | TRANSFER_OUT                  |
| type           | POSITION_BUY                  |
| type           | POSITION_SELL                 |
| type           | POSITION_FUNDING             |
| type           | FILL_FEE_INCOME               |
| type           | BUG_FIX_COLLATERAL_TRANSACTION_TYPE  |
| type           | UNRECOGNIZED                  |
| transferReason | UNKNOWN_TRANSFER_REASON       |
| transferReason | USER_TRANSFER                |
| transferReason | FAST_WITHDRAW                  |
| transferReason | CROSS_DEPOSIT                |
| transferReason | CROSS_WITHDRAW              |
| transferReason | UNRECOGNIZED                  |
| censorStatus   | UNKNOWN_TRANSACTION_STATUS      |
| censorStatus   | INIT                        |
| censorStatus   | CENSOR_SUCCESS                 |
| censorStatus   | CENSOR_FAILURE               |
| censorStatus   | L2_APPROVED                   |
| censorStatus   | L2_REJECT                     |
| censorStatus   | L2_REJECT_APPROVED             |
| censorStatus   | UNRECOGNIZED                   |

<h2 id="tocS_Result<PageData<CollateralTransaction>>">Result&lt;PageData&lt;CollateralTransaction&gt;&gt;</h2>

<a id="schemaresult<pagedata<collateraltransaction>>"></a>
<a id="schema_Result<PageData<CollateralTransaction>>"></a>
<a id="tocSresult<pagedata<collateraltransaction>>"></a>
<a id="tocsresult<pagedata<collateraltransaction>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
        "deltaAmount": "string",
        "deltaLegacyAmount": "string",
        "beforeAmount": "string",
        "beforeLegacyAmount": "string",
        "fillCloseSize": "string",
        "fillCloseValue": "string",
        "fillCloseFee": "string",
        "fillOpenSize": "string",
        "fillOpenValue": "string",
        "fillOpenFee": "string",
        "fillPrice": "string",
        "liquidateFee": "string",
        "realizePnl": "string",
        "isLiquidate": true,
        "isDeleverage": true,
        "fundingTime": "string",
        "fundingRate": "string",
        "fundingIndexPrice": "string",
        "fundingOraclePrice": "string",
        "fundingPositionSize": "string",
        "depositId": "string",
        "withdrawId": "string",
        "transferInId": "string",
        "transferOutId": "string",
        "transferReason": "UNKNOWN_TRANSFER_REASON",
        "orderId": "string",
        "orderFillTransactionId": "string",
        "orderAccountId": "string",
        "positionContractId": "string",
        "positionTransactionId": "string",
        "forceWithdrawId": "string",
        "forceTradeId": "string",
        "extraType": "string",
        "extraDataJson": "string",
        "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
        "censorTxId": "string",
        "censorTime": "string",
        "censorFailCode": "string",
        "censorFailReason": "string",
        "l2TxId": "string",
        "l2RejectTime": "string",
        "l2RejectCode": "string",
        "l2RejectReason": "string",
        "l2ApprovedTime": "string",
        "createdTime": "string",
        "updatedTime": "string"
      }
    ],
    "nextPageOffsetData": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                                     | Required | Constraints | Description                        | Notes                                                                  |
| -------------- | ---------------------------------------- | -------- | ----------- | ---------------------------------- | ---------------------------------------------------------------------- |
| code           | string                                   | false    | none        | Status Code                        | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [PageDataCollateralTransaction](#schemapagedatacollateraltransaction) | false    | none        | Generic Paginated Response | Generic paginated response.                                                              |
| errorParam     | object                                   | false    | none        | Error Parameters                   | Error message parameter information                                     |
| » **additionalProperties** | string                                   | false    | none        | Error Parameters                   | Error message parameter information                                     |
| requestTime    | string(timestamp)                        | false    | none        | Server Request Time               | Time at which the server received the request                           |
| responseTime   | string(timestamp)                        | false    | none        | Server Response Time              | Time at which the server sent the response                              |
| traceId        | string                                   | false    | none        | Trace ID                          | Invocation trace ID                                                  |

<h2 id="tocS_PageDataCollateralTransaction">PageDataCollateralTransaction</h2>

<a id="schemapagedatacollateraltransaction"></a>
<a id="schema_PageDataCollateralTransaction"></a>
<a id="tocSpagedatacollateraltransaction"></a>
<a id="tocspagedatacollateraltransaction"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
      "deltaAmount": "string",
      "deltaLegacyAmount": "string",
      "beforeAmount": "string",
      "beforeLegacyAmount": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "depositId": "string",
      "withdrawId": "string",
      "transferInId": "string",
      "transferOutId": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "orderAccountId": "string",
      "positionContractId": "string",
      "positionTransactionId": "string",
      "forceWithdrawId": "string",
      "forceTradeId": "string",
      "extraType": "string",
      "extraDataJson": "string",
      "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2RejectTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l2ApprovedTime": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "nextPageOffsetData": "string"
}
```

Generic Paginated Response

### Properties

| Name               | Type                             | Required | Constraints | Description                 | Notes                                                               |
| ------------------ | -------------------------------- | -------- | ----------- | --------------------------- | ------------------------------------------------------------------- |
| dataList           | [[CollateralTransaction](#schemacollateraltransaction)] | false    | none        | Data List                  | List of collateral transaction data.                                               |
| nextPageOffsetData | string                           | false    | none        | Next Page Offset        | Offset for retrieving the next page. If no next page data, empty string. |

<h2 id="tocS_Result<List<Position>>">Result&lt;List&lt;Position&gt;&gt;</h2>

<a id="schemaresult<list<position>>"></a>
<a id="schema_Result<List<Position>>"></a>
<a id="tocSresult<list<position>>"></a>
<a id="tocsresult<list<position>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "openSize": "string",
      "openValue": "string",
      "openFee": "string",
      "fundingFee": "string",
      "longTermCount": 0,
      "longTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "longTermCreatedTime": "string",
      "longTermUpdatedTime": "string",
      "shortTermCount": 0,
      "shortTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTermCreatedTime": "string",
      "shortTermUpdatedTime": "string",
      "longTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                   | Required | Constraints | Description        | Notes                                                                  |
| -------------- | ---------------------- | -------- | ----------- | ------------------ | ---------------------------------------------------------------------- |
| code           | string                 | false    | none        | Status Code        | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [[Position](#schemaposition)] | false    | none        | Response Data     | Correct response data.                                                  |
| errorParam     | object                 | false    | none        | Error Parameters   | Error message parameter information                                     |
| » **additionalProperties** | string                 | false    | none        | Error Parameters   | Error message parameter information                                     |
| requestTime    | string(timestamp)      | false    | none        | Server Request Time | Time at which the server received the request                           |
| responseTime   | string(timestamp)      | false    | none        | Server Response Time| Time at which the server sent the response                              |
| traceId        | string                 | false    | none        | Trace ID           | Invocation trace ID                                                  |

<h2 id="tocS_Result<PageData<PositionTerm>>">Result&lt;PageData&lt;PositionTerm&gt;&gt;</h2>

<a id="schemaresult<pagedata<positionterm>>"></a>
<a id="schema_Result<PageData<PositionTerm>>"></a>
<a id="tocSresult<pagedata<positionterm>>"></a>
<a id="tocsresult<pagedata<positionterm>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "termCount": 0,
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string",
        "createdTime": "string",
        "updatedTime": "string",
        "currentLeverage": "string"
      }
    ],
    "nextPageOffsetData": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                                   | Required | Constraints | Description                | Notes                                                                    |
| -------------- | -------------------------------------- | -------- | ----------- | -------------------------- | ------------------------------------------------------------------------ |
| code           | string                                 | false    | none        | Status Code                | Returns "SUCCESS" on success; otherwise, it indicates failure.            |
| data           | [PageDataPositionTerm](#schemapagedatapositionterm)  | false    | none        | Generic Paginated Response | Generic paginated response.                                                              |
| errorParam     | object                                 | false    | none        | Error Parameters           | Error message parameter information                                       |
| » **additionalProperties** | string                                 | false    | none        | Error Parameters           | Error message parameter information                                       |
| requestTime    | string(timestamp)                      | false    | none        | Server Request Time       | Time at which the server received the request                           |
| responseTime   | string(timestamp)                      | false    | none        | Server Response Time      | Time at which the server sent the response                              |
| traceId        | string                                 | false    | none        | Trace ID                  | Invocation trace ID                                                     |

<h2 id="tocS_PageDataPositionTerm">PageDataPositionTerm</h2>

<a id="schemapagedatapositionterm"></a>
<a id="schema_PageDataPositionTerm"></a>
<a id="tocSpagedatapositionterm"></a>
<a id="tocspagedatapositionterm"></a>

```json
{
  "dataList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId":"string",
      "termCount": 0,
      "cumOpenSize": "string",
      "cumOpenValue": "string",
      "cumOpenFee": "string",
      "cumCloseSize": "string",
      "cumCloseValue": "string",
      "cumCloseFee": "string",
      "cumFundingFee": "string",
      "cumLiquidateFee": "string",
      "createdTime": "string",
      "updatedTime": "string",
      "currentLeverage": "string"
    }
  ],
  "nextPageOffsetData": "string"
}
```

Generic Paginated Response

### Properties

| Name               | Type                           | Required | Constraints | Description                 | Notes                                                               |
| ------------------ | ------------------------------ | -------- | ----------- | --------------------------- | ------------------------------------------------------------------- |
| dataList           | [[PositionTerm](#schemapositionterm)] | false    | none        | Data List                  | List of position term data.                                                    |
| nextPageOffsetData | string                         | false    | none        | Next Page Offset        | Offset for retrieving the next page. If no next page data, empty string. |

<h2 id="tocS_PositionTerm">PositionTerm</h2>

<a id="schemapositionterm"></a>
<a id="schema_PositionTerm"></a>
<a id="tocSpositionterm"></a>
<a id="tocspositionterm"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "termCount": 0,
  "cumOpenSize": "string",
  "cumOpenValue": "string",
  "cumOpenFee": "string",
  "cumCloseSize": "string",
  "cumCloseValue": "string",
  "cumCloseFee": "string",
  "cumFundingFee": "string",
  "cumLiquidateFee": "string",
  "createdTime": "string",
  "updatedTime": "string",
  "currentLeverage": "string"
}
```

Position term information.

### Properties

| Name            | Type          | Required | Constraints | Description                         | Notes                                                                        |
| --------------- | ------------- | -------- | ----------- | ----------------------------------- | ---------------------------------------------------------------------------- |
| userId          | string        | false    | none        | User ID                             | ID of the owning user.                                                                     |
| accountId       | string        | false    | none        | Account ID                          | ID of the owning account.                                                                   |
| coinId          | string        | false    | none        | Collateral Coin ID                 | ID of the associated collateral coin.                                                 |
| contractId      | string        | false    | none        | Contract ID                         | ID of the associated contract.                                                           |
| termCount       | integer(int32) | false    | none        | Term Count                          | Term count. Starts from 1, increases by one each time a position is fully closed and then re-opened.        |
| cumOpenSize     | string        | false    | none        | Cumulative Open Size                | Cumulative open size.                                                               |
| cumOpenValue    | string        | false    | none        | Cumulative Open Value              | Cumulative open value.                                                              |
| cumOpenFee      | string        | false    | none        | Cumulative Open Fee                | Cumulative open fees.                                                                |
| cumCloseSize    | string        | false    | none        | Cumulative Close Size              | Cumulative close size.                                                              |
| cumCloseValue   | string        | false    | none        | Cumulative Close Value             | Cumulative close value.                                                                |
| cumCloseFee     | string        | false    | none        | Cumulative Close Fee               | Cumulative close fees.                                                               |
| cumFundingFee   | string        | false    | none        | Cumulative Funding Fee            | Cumulative funding fees that have been settled.                                |
| cumLiquidateFee | string        | false    | none        | Cumulative Liquidation Fee          | Cumulative liquidation fees.                                                       |
| createdTime     | string(int64) | false    | none        | Creation Time                      | Creation time.                                                                      |
| updatedTime     | string(int64) | false    | none        | Update Time                        | Update time.                                                                      |
| currentLeverage | string        | false    | none        | Leverage at Close             | Leverage multiple at the time of close position.                                                      |

<h2 id="tocS_Result<List<PositionTransaction>>">Result&lt;List&lt;PositionTransaction&gt;&gt;</h2>

<a id="schemaresult<list<positiontransaction>>"></a>
<a id="schema_Result<List<PositionTransaction>>"></a>
<a id="tocSresult<list<positiontransaction>>"></a>
<a id="tocsresult<list<positiontransaction>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "type": "UNKNOWN_POSITION_TRANSACTION_TYPE",
      "deltaOpenSize": "string",
      "deltaOpenValue": "string",
      "deltaOpenFee": "string",
      "deltaFundingFee": "string",
      "beforeOpenSize": "string",
      "beforeOpenValue": "string",
      "beforeOpenFee": "string",
      "beforeFundingFee": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "collateralTransactionId": "string",
      "forceTradeId": "string",
      "extraType": "string",
      "extraDataJson": "string",
      "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2RejectTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l2ApprovedTime": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                                 | Required | Constraints | Description        | Notes                                                                  |
| -------------- | ------------------------------------ | -------- | ----------- | ------------------ | ---------------------------------------------------------------------- |
| code           | string                               | false    | none        | Status Code        | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [[PositionTransaction](#schemapositiontransaction)] | false    | none        | Response Data     | Correct response data.                                                  |
| errorParam     | object                               | false    | none        | Error Parameters   | Error message parameter information                                     |
| » **additionalProperties** | string                               | false    | none        | Error Parameters   | Error message parameter information                                     |
| requestTime    | string(timestamp)                    | false    | none        | Server Request Time | Time at which the server received the request                           |
| responseTime   | string(timestamp)                    | false    | none        | Server Response Time| Time at which the server sent the response                              |
| traceId        | string                               | false    | none        | Trace ID           | Invocation trace ID                                                  |

<h2 id="tocS_PositionTransaction">PositionTransaction</h2>

<a id="schemapositiontransaction"></a>
<a id="schema_PositionTransaction"></a>
<a id="tocSpositiontransaction"></a>
<a id="tocspositiontransaction"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "type": "UNKNOWN_POSITION_TRANSACTION_TYPE",
  "deltaOpenSize": "string",
  "deltaOpenValue": "string",
  "deltaOpenFee": "string",
  "deltaFundingFee": "string",
  "beforeOpenSize": "string",
  "beforeOpenValue": "string",
  "beforeOpenFee": "string",
  "beforeFundingFee": "string",
  "fillCloseSize": "string",
  "fillCloseValue": "string",
  "fillCloseFee": "string",
  "fillOpenSize": "string",
  "fillOpenValue": "string",
  "fillOpenFee": "string",
  "fillPrice": "string",
  "liquidateFee": "string",
  "realizePnl": "string",
  "isLiquidate": true,
  "isDeleverage": true,
  "fundingTime": "string",
  "fundingRate": "string",
  "fundingIndexPrice": "string",
  "fundingOraclePrice": "string",
  "fundingPositionSize": "string",
  "orderId": "string",
  "orderFillTransactionId": "string",
  "collateralTransactionId": "string",
  "forceTradeId": "string",
  "extraType": "string",
  "extraDataJson": "string",
  "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
  "censorTxId": "string",
  "censorTime": "string",
  "censorFailCode": "string",
  "censorFailReason": "string",
  "l2TxId": "string",
  "l2RejectTime": "string",
  "l2RejectCode": "string",
  "l2RejectReason": "string",
  "l2ApprovedTime": "string",
  "createdTime": "string",
  "updatedTime": "string"
}
```

Perpetual contract position transaction details.

### Properties

| Name                    | Type          | Required | Constraints | Description                                                                              | Notes                                                                                            |
| ----------------------- | ------------- | -------- | ----------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| id                      | string(int64) | false    | none        | Unique Identifier                                                                        | Unique identifier.                                                                               |
| userId                  | string(int64) | false    | none        | User ID                                                                                  | ID of the owning user.                                                                         |
| accountId               | string(int64) | false    | none        | Account ID                                                                               | ID of the owning account.                                                                      |
| coinId                  | string(int64) | false    | none        | Collateral Coin ID                                                                       | ID of the associated collateral coin.                                                            |
| contractId              | string(int64) | false    | none        | Contract ID                                                                               | ID of the associated contract.                                                                  |
| type                    | string        | false    | none        | Detail Type                                                                              | Detail type.                                                                                     |
| deltaOpenSize           | string        | false    | none        | Change in Open Size                                                                    | Change in holding size.                                                                         |
| deltaOpenValue          | string        | false    | none        | Change in Open Value                                                                   | Change in open value.                                                                          |
| deltaOpenFee            | string        | false    | none        | Change in Open Fee                                                                      | Change in open fee.                                                                           |
| deltaFundingFee         | string        | false    | none        | Change in Funding Fee                                                                   | Change in funding fee.                                                                        |
| beforeOpenSize          | string        | false    | none        | Open Size Before Change                                                                | Holding size before the change.                                                                  |
| beforeOpenValue         | string        | false    | none        | Open Value Before Change                                                               | Open value before the change.                                                                   |
| beforeOpenFee           | string        | false    | none        | Open Fee Before Change                                                                 | Open fee before the change.                                                                    |
| beforeFundingFee        | string        | false    | none        | Funding Fee Before Change                                                              | Funding fee before the change.                                                                  |
| fillCloseSize           | string        | false    | none        | Transaction Close Size                                                                  | Transaction close size (positive for buy, negative for sell).                                          |
| fillCloseValue          | string        | false    | none        | Transaction Close Value                                                                  | Transaction close value (positive for buy, negative for sell).                                      |
| fillCloseFee            | string        | false    | none        | Transaction Close Fee                                                                     | Transaction close fee (typically zero or negative).                                            |
| fillOpenSize            | string        | false    | none        | Transaction Open Size                                                                  | Transaction open size (positive for buy, negative for sell).                                          |
| fillOpenValue           | string        | false    | none        | Transaction Open Value                                                                   | Transaction open value (positive for buy, negative for sell).                                      |
| fillOpenFee             | string        | false    | none        | Transaction Open Fee                                                                      | Transaction open fee (typically zero or negative).                                            |
| fillPrice               | string        | false    | none        | Transaction Price                                                                         | Transaction price (not precise, for display).                                              |
| liquidateFee            | string        | false    | none        | Liquidation Fee                                                                           | Liquidation fee (if close transaction is a liquidation, typically zero or negative).          |
| realizePnl              | string        | false    | none        | Realized Profit and Loss                                                                 | Realized profit and loss from a close (if a close transaction. Not precise, for display). |
| isLiquidate             | boolean       | false    | none        | Is Liquidation                                                                             | Whether the transaction is a liquidation.                                                       |
| isDeleverage            | boolean       | false    | none        | Is Auto-Deleveraging                                                                      | Whether the transaction is from auto-deleveraging.                                              |
| fundingTime             | string(int64) | false    | none        | Funding Settlement Time                                                                  | Funding settlement time.                                                                       |
| fundingRate             | string        | false    | none        | Funding Rate                                                                             | Funding rate.                                                                                   |
| fundingIndexPrice       | string        | false    | none        | Funding Index Price                                                                     | Index price related to funding rate.                                                         |
| fundingOraclePrice      | string        | false    | none        | Funding Oracle Price                                                                    | Oracle price related to funding rate.                                                        |
| fundingPositionSize     | string        | false    | none        | Position Size During Funding Settlement                                                  | Position size during funding settlement (positive for long, negative for short).               |
| orderId                 | string(int64) | false    | none        | Order ID                                                                                  | Associated order ID.                                                                              |
| orderFillTransactionId  | string(int64) | false    | none        | Order Fill Transaction ID                                                               | Associated order fill transaction ID.                                                       |
| collateralTransactionId | string(int64) | false    | none        | Collateral Transaction ID                                                             | Associated collateral transaction detail ID.                                                |
| forceTradeId            | string        | false    | none        | Force Trade ID                                                                            | Associated force trade order ID.                                                               |
| extraType               | string        | false    | none        | Extra Type                                                                               | Extra type for upper-layer business use.                                                     |
| extraDataJson           | string        | false    | none        | Extra Data                                                                              | Extra data in JSON format, default is empty string.                                           |
| censorStatus            | string        | false    | none        | Current Censoring Status                                                                  | Current censoring status.                                                                       |
| censorTxId              | string(int64) | false    | none        | Censoring Processing Sequence Number                                                       | Censoring processing sequence number, exists when censor_status=CENSOR_SUCCESS/CENSOR_FAILURE/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED.   |
| censorTime              | string(int64) | false    | none        | Censoring Processing Time                                                                   | Censoring processing time, exists when censor_status=CENSOR_SUCCESS/CENSOR_FAILURE/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED.   |
| censorFailCode          | string        | false    | none        | Censoring Failure Code                                                                     | Censoring failure code, exists when censor_status=CENSOR_FAILURE.                              |
| censorFailReason        | string        | false    | none        | Censoring Failure Reason                                                                   | Censoring failure reason, exists when censor_status=CENSOR_FAILURE.                            |
| l2TxId                  | string(int64) | false    | none        | L2 Push Transaction ID                                                                  | L2 push transaction ID, exists when censor_status=CENSOR_SUCCESS/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED.   |
| l2RejectTime            | string(int64) | false    | none        | L2 Rejection Time                                                                        | L2 rejection time, exists when censor_status=L2_REJECT/L2_REJECT_APPROVED.                  |
| l2RejectCode            | string        | false    | none        | L2 Rejection Error Code                                                                    | L2 rejection error code, exists when censor_status=L2_REJECT/L2_REJECT_APPROVED.               |
| l2RejectReason          | string        | false    | none        | L2 Rejection Reason                                                                      | L2 rejection reason, exists when censor_status=L2_REJECT/L2_REJECT_APPROVED.                  |
| l2ApprovedTime          | string(int64) | false    | none        | L2 Batch Verification Time                                                               | L2 batch verification time, exists when censor_status=L2_APPROVED/L2_REJECT_APPROVED.          |
| createdTime             | string(int64) | false    | none        | Creation Time                                                                                | Creation time.                                                                                  |
| updatedTime             | string(int64) | false    | none        | Update Time                                                                               | Update time.                                                                                    |

#### Enumerated Values

| Property     | Value                         |
| ------------ | ----------------------------- |
| type         | UNKNOWN_POSITION_TRANSACTION_TYPE     |
| type         | BUY_POSITION                |
| type         | SELL_POSITION                |
| type         | SETTLE_FUNDING_FEE            |
| type         | BUG_FIX_POSITION_TRANSACTION_TYPE      |
| type         | UNRECOGNIZED                 |
| censorStatus | UNKNOWN_TRANSACTION_STATUS     |
| censorStatus | INIT                         |
| censorStatus | CENSOR_SUCCESS                 |
| censorStatus | CENSOR_FAILURE               |
| censorStatus | L2_APPROVED                    |
| censorStatus | L2_REJECT                      |
| censorStatus | L2_REJECT_APPROVED            |
| censorStatus | UNRECOGNIZED                  |

<h2 id="tocS_Result<PageData<PositionTransaction>>">Result&lt;PageData&lt;PositionTransaction&gt;&gt;</h2>

<a id="schemaresult<pagedata<positiontransaction>>"></a>
<a id="schema_Result<PageData<PositionTransaction>>"></a>
<a id="tocSresult<pagedata<positiontransaction>>"></a>
<a id="tocsresult<pagedata<positiontransaction>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "type": "UNKNOWN_POSITION_TRANSACTION_TYPE",
        "deltaOpenSize": "string",
        "deltaOpenValue": "string",
        "deltaOpenFee": "string",
        "deltaFundingFee": "string",
        "beforeOpenSize": "string",
        "beforeOpenValue": "string",
        "beforeOpenFee": "string",
        "beforeFundingFee": "string",
        "fillCloseSize": "string",
        "fillCloseValue": "string",
        "fillCloseFee": "string",
        "fillOpenSize": "string",
        "fillOpenValue": "string",
        "fillOpenFee": "string",
        "fillPrice": "string",
        "liquidateFee": "string",
        "realizePnl": "string",
        "isLiquidate": true,
        "isDeleverage": true,
        "fundingTime": "string",
        "fundingRate": "string",
        "fundingIndexPrice": "string",
        "fundingOraclePrice": "string",
        "fundingPositionSize": "string",
        "orderId": "string",
        "orderFillTransactionId": "string",
        "collateralTransactionId": "string",
        "forceTradeId": "string",
        "extraType": "string",
        "extraDataJson": "string",
        "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
        "censorTxId": "string",
        "censorTime": "string",
        "censorFailCode": "string",
        "censorFailReason": "string",
        "l2TxId": "string",
        "l2RejectTime": "string",
        "l2RejectCode": "string",
        "l2RejectReason": "string",
        "l2ApprovedTime": "string",
        "createdTime": "string",
        "updatedTime": "string"
      }
    ],
    "nextPageOffsetData": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                                       | Required | Constraints | Description                        | Notes                                                                  |
| -------------- | ------------------------------------------ | -------- | ----------- | ---------------------------------- | ---------------------------------------------------------------------- |
| code           | string                                     | false    | none        | Status Code                        | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [PageDataPositionTransaction](#schemapagedatapositiontransaction) | false    | none        | Generic Paginated Response         | Generic paginated response.                                                              |
| errorParam     | object                                     | false    | none        | Error Parameters                   | Error message parameter information                                     |
| » **additionalProperties** | string                                     | false    | none        | Error Parameters                   | Error message parameter information                                     |
| requestTime    | string(timestamp)                          | false    | none        | Server Request Time               | Time at which the server received the request                           |
| responseTime   | string(timestamp)                          | false    | none        | Server Response Time              | Time at which the server sent the response                              |
| traceId        | string                                     | false    | none        | Trace ID                          | Invocation trace ID                                                  |

<h2 id="tocS_PageDataPositionTransaction">PageDataPositionTransaction</h2>

<a id="schemapagedatapositiontransaction"></a>
<a id="schema_PageDataPositionTransaction"></a>
<a id="tocSpagedatapositiontransaction"></a>
<a id="tocspagedatapositiontransaction"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "type": "UNKNOWN_POSITION_TRANSACTION_TYPE",
      "deltaOpenSize": "string",
      "deltaOpenValue": "string",
      "deltaOpenFee": "string",
      "deltaFundingFee": "string",
      "beforeOpenSize": "string",
      "beforeOpenValue": "string",
      "beforeOpenFee": "string",
      "beforeFundingFee": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "collateralTransactionId": "string",
      "forceTradeId": "string",
      "extraType": "string",
      "extraDataJson": "string",
      "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2RejectTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l2ApprovedTime": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "nextPageOffsetData": "string"
}
```

Generic Paginated Response

### Properties

| Name               | Type                                  | Required | Constraints | Description                 | Notes                                                               |
| ------------------ | ------------------------------------- | -------- | ----------- | --------------------------- | ------------------------------------------------------------------- |
| dataList           | [[PositionTransaction](#schemapositiontransaction)] | false    | none        | Data List                  | List of position transaction data.                                          |
| nextPageOffsetData | string                                | false    | none        | Next Page Offset        | Offset for retrieving the next page. If no next page data, empty string. |

<h2 id="tocS_Result<RegisterAccount>">Result&lt;RegisterAccount&gt;</h2>

<a id="schemaresult<registeraccount>"></a>
<a id="schema_Result<RegisterAccount>"></a>
<a id="tocSresult<registeraccount>"></a>
<a id="tocsresult<registeraccount>"></a>

```json
{
  "code": "string",
  "data": {
    "accountId": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type                      | Required | Constraints | Description          | Notes                                                                  |
| -------------- | ------------------------- | -------- | ----------- | -------------------- | ---------------------------------------------------------------------- |
| code           | string                    | false    | none        | Status Code          | Returns "SUCCESS" on success; otherwise, it indicates failure.          |
| data           | [RegisterAccount](#schemaregisteraccount) | false    | none        | Register Account Response | Response structure for registering an account.                         |
| errorParam     | object                    | false    | none        | Error Parameters     | Error message parameter information                                     |
| » **additionalProperties** | string                    | false    | none        | Error Parameters     | Error message parameter information                                     |
| requestTime    | string(timestamp)         | false    | none        | Server Request Time  | Time at which the server received the request                           |
| responseTime   | string(timestamp)         | false    | none        | Server Response Time | Time at which the server sent the response                              |
| traceId        | string                    | false    | none        | Trace ID             | Invocation trace ID                                                  |

<h2 id="tocS_RegisterAccount">RegisterAccount</h2>

<a id="schemaregisteraccount"></a>
<a id="schema_RegisterAccount"></a>
<a id="tocSregisteraccount"></a>
<a id="tocsregisteraccount"></a>

```json
{
  "accountId": "string"
}
```

Response structure for registering an account.

### Properties

| Name      | Type          | Required | Constraints | Description | Notes             |
| --------- | ------------- | -------- | ----------- | ----------- | ----------------- |
| accountId | string(int64) | false    | none        | Account ID  | Account ID.       |

<h2 id="tocS_RegisterAccountParam">RegisterAccountParam</h2>

<a id="schemaregisteraccountparam"></a>
<a id="schema_RegisterAccountParam"></a>
<a id="tocSregisteraccountparam"></a>
<a id="tocsregisteraccountparam"></a>

```json
{
  "l2Key": "string",
  "l2KeyYCoordinate": "string",
  "clientAccountId": "string"
}
```

Request structure for registering an account.

### Properties

| Name             | Type   | Required | Constraints | Description                                                                         | Notes                                                           |
| ---------------- | ------ | -------- | ----------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| l2Key            | string | false    | none        | L2 Account Key                                                                      | Account key on L2, globally unique. Stark key in starkEx. Bigint for hex string. |
| l2KeyYCoordinate | string | false    | none        | L2 Key Y Coordinate                                                               | Used only for verifying l2Signature. Not returned to end users. Bigint for hex string. |
| clientAccountId  | string | false    | none        | Client Account ID                                                                   | Client account ID for idempotency check.                         |

<h2 id="tocS_UpdateFeeSettingParam">UpdateFeeSettingParam</h2>

<a id="schemaupdatefeesettingparam"></a>
<a id="schema_UpdateFeeSettingParam"></a>
<a id="tocSupdatefeesettingparam"></a>
<a id="tocsupdatefeesettingparam"></a>

```json
{
  "accountId": "string",
  "contractId": "string",
  "isSetFeeRate": true,
  "takerFeeRate": "string",
  "makerFeeRate": "string",
  "isSetFeeDiscount": true,
  "takerFeeDiscount": "string",
  "makerFeeDiscount": "string"
}
```

Request structure for updating account trading fee settings.

### Properties

| Name             | Type          | Required | Constraints | Description                                                                                        | Notes                                                                                             |
| ---------------- | ------------- | -------- | ----------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| accountId        | string(int64) | false    | none        | Account ID                                                                                           | Account ID.                                                                                        |
| contractId       | string(int64) | false    | none        | Contract ID                                                                                       | Contract ID, if 0, will change the default fee settings for the account.                               |
| isSetFeeRate     | boolean       | false    | none        | Whether Fee Rate Is Set                                                                            | Whether to set a specific fee rate value.                                                                |
| takerFeeRate     | string        | false    | none        | Taker Fee Rate                                                                                     | Taker fee rate, range [0, 1), valid only when is_set_fee_rate=true.                                 |
| makerFeeRate     | string        | false    | none        | Maker Fee Rate                                                                                     | Maker fee rate, range [0, 1), valid only when is_set_fee_rate=true.                                 |
| isSetFeeDiscount | boolean       | false    | none        | Whether Fee Discount Is Set                                                                       | Whether to set a fee discount.                                                                    |
| takerFeeDiscount | string        | false    | none        | Taker Fee Discount                                                                                  | Taker fee discount.                                                                         |
| makerFeeDiscount | string        | false    | none        | Maker Fee Discount                                                                                  | Maker fee discount.                                                                        |

<h2 id="tocS_Result">Result</h2>

<a id="schemaresult"></a>
<a id="schema_Result"></a>
<a id="tocSresult"></a>
<a id="tocsresult"></a>

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

Generic response structure.

### Properties

| Name         | Type    | Required | Constraints | Description                                       | Notes                                                               |
| ------------ | ------- | -------- | ----------- | ------------------------------------------------- | ------------------------------------------------------------------- |
| code         | string  | false    | none        | Status Code                                       | Returns "SUCCESS" on success; otherwise, it indicates failure.        |
| msg          | string  | false    | none        | Detailed Error Message                            | Detailed error message when an error occurs.                            |
| requestTime  | string(int64) | false    | none        | Server Request Time                             | Time at which the server received the request.                             |
| responseTime | string(int64) | false    | none        | Server Response Time                            | Time at which the server sent the response.                            |

<h2 id="tocS_Result<Void>">Result&lt;Void&gt;</h2>

<a id="schemaresult<void>"></a>
<a id="schema_Result<Void>"></a>
<a id="tocSresult<void>"></a>
<a id="tocsresult<void>"></a>

```json
{
  "code": "string",
  "data": {},
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### Properties

| Name           | Type     | Required | Constraints | Description          | Notes                                                                  |
| -------------- | -------- | -------- | ----------- | -------------------- | ---------------------------------------------------------------------- |
| code           | string   | false    | none        | Status Code          | Returns "SUCCESS" onsuccess; otherwise, it indicates failure.          |
| data           | object   | false    | none        | Response Data        | Correct response data.                                                  |
| errorParam     | object   | false    | none        | Error Parameters     | Error message parameter information                                     |
| » **additionalProperties** | string   | false    | none        | Error Parameters     | Error message parameter information                                     |
| requestTime    | string(timestamp) | false    | none        | Server Request Time  | Time at which the server received the request                           |
| responseTime   | string(timestamp) | false    | none        | Server Response Time | Time at which the server sent the response                              |
| traceId        | string   | false    | none        | Trace ID             | Invocation trace ID                                                  |

<h2 id="tocS_UpdateLeverageSettingParam">UpdateLeverageSettingParam</h2>

<a id="schemaupdateleveragesettingparam"></a>
<a id="schema_UpdateLeverageSettingParam"></a>
<a id="tocSupdateleveragesettingparam"></a>
<a id="tocsupdateleveragesettingparam"></a>

```json
{
  "accountId": "string",
  "contractId": "string",
  "leverage": "string"
}
```

Request structure for updating account trading leverage settings.

### Properties

| Name       | Type          | Required | Constraints | Description                                                                    | Notes                                                                                    |
| ---------- | ------------- | -------- | ----------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| accountId  | string(int64) | false    | none        | Account ID                                                                      | Account ID.                                                                              |
| contractId | string(int64) | false    | none        | Contract ID                                                                   | Contract ID, if 0, will change the default leverage settings for the account.                     |
| leverage   | string        | false    | none        | Leverage Multiple                                                                    | Leverage multiple.                                                      |

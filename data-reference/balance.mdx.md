---
title: 'Balance'
description: 'Represents a balance in the CAMT.053 format'
icon: 'money-bill'
---

### Balance

The `Balance` interface represents a balance in the CAMT.053 format.

```typescript
interface Balance {
type: BalanceType;
amount: number;
currency: string;
  date: Date;
  creditDebitIndicator: 'credit' | 'debit';
}
```

<ParamField body="type" type="BalanceType">
  The type of balance (e.g., opening, closing, intermediate).
</ParamField>

<ParamField body="amount" type="number">
  The balance amount.
</ParamField>

<ParamField body="currency" type="string">
  The currency of the balance, typically represented as a 3-letter ISO currency code.
</ParamField>

<ParamField body="date" type="Date">
  The date associated with this balance.
</ParamField>

<ParamField body="creditDebitIndicator" type="string">
  Indicates whether the balance is a credit ('credit') or debit ('debit').
</ParamField>

# Balance Types

The `BalanceTypeCodes` contains balance types as defined in ISO20022. These codes are used to specify different types of balances in financial transactions and reports.

| Code | Description |
|------|-------------|
| `ClosingAvailable` | Closing balance of amount of money that is at the disposal of the account owner on the date specified. |
| `ClosingBooked` | Balance of the account at the end of the pre-agreed account reporting period. It is the sum of the opening booked balance at the beginning of the period and all entries booked to the account during the pre-agreed account reporting period. |
| `ForwardAvailable` | Forward available balance of money that is at the disposal of the account owner on the date specified. |
| `Information` | Balance for informational purposes. |
| `InterimAvailable` | Available balance calculated in the course of the account servicer's business day, at the time specified, and subject to further changes during the business day. The interim balance is calculated on the basis of booked credit and debit items during the calculation time/period specified. |
| `InterimBooked` | Balance calculated in the course of the account servicer's business day, at the time specified, and subject to further changes during the business day. The interim balance is calculated on the basis of booked credit and debit items during the calculation time/period specified. |
| `OpeningAvailable` | Opening balance of amount of money that is at the disposal of the account owner on the date specified. |
| `OpeningBooked` | Book balance of the account at the beginning of the account reporting period. It always equals the closing book balance from the previous report. |
| `PreviouslyClosedBooked` | Balance of the account at the previously closed account reporting period. The opening booked balance for the new period has to be equal to this balance. Usage: the previously booked closing balance should equal (inclusive date) the booked closing balance of the date it references and equal the actual booked opening balance of the current date. |
| `Expected` | Balance, composed of booked entries and pending items known at the time of calculation, which projects the end of day balance if everything is booked on the account and no other entry is posted. |
| `AdditionalBalReserveRequirement` | The difference between the excess/(deficit) investable balance and the excess/(deficit) collected balance due to the reserve requirement. This balance is not used if the account's Earnings Credit Rate is net of reserves. This may be used when the earnings allowance rate is not adjusted for reserves. It may be that reserves have been subtracted from the collected balance to determine the investable balance. Therefore, they must be added back to the excess/(deficit) investable balance to determine the collected balance position. The presentation of this calculation is optional. AFP code=00 04 21 |

## Reference

For more information about these balance types and their usage in ISO 20022, please refer to the [official ISO 20022 external code sets](https://www.iso20022.org/sites/default/files/2022-03/externalcodesets_4q2021_v2_1.xlsx).
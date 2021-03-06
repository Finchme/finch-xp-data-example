# Finch XP API Test Data

Testing the Finch XP APIs is simple and doesn't require you to use real transactional data thanks to our test data.

The Finch XP Test data consists of 100 transactions from fake users at 4 fake financial institutions/banks. You will have to specify the `productType` you are currently subscribed to in the request body.

You are welcome to test using your own real data although testing (both fake and real data) is limited to 1000 transactions, 100 users, or 90 days: whichever is first.

If you would like to test with your own data, please [contact us](mailto:sales@finchxp.com) and we’ll provide you with a list of financial institutions/banks that we support for testing.

To see a full list of all financial institutions/banks we support in production, check out our providers list [here](https://docs.finchxp.com).

# Using the Real-time Service API

The required parameters for each request sent to the Finch XP APIs are listed below:

##### ExternalUser
|   Name   |    Type    |   Description |
|---|---|---|
|externalUserId|string|The unique ID used to identify your customer and their data on FinchXP. This must be defined by you.|

##### AccountEntity
|   Name   |    Type    |   Description |
|---|---|---|
|providerId|string|The bank or financial institution of the end-user. See GET `/api/providers` for a list of providers and their providerIDs|
|externalAccountId|string|The account number as provided by the bank or financial institution|
|accountType|string| The type of financial account as defined by the bank or financial institution, e.g. checking, savings, loan etc|

##### ProcessTransactionEntity
|   Name   |    Type    |   Description |
|---|---|---|
|externalTransactionId|string| The unique transaction number as defined by you, the bank or financial institution. Each transaction belongs to only one account|
|type|enum|A transaction type represents a money movement in or out of an account. `CREDIT` is money in, income etc.; `DEBIT` is money out, expense|
|description|string|The original description of the transaction as provided by the institution i.e. as it appears in the original bank statement |
|postDate|string|The posted date of the transaction as provided by the institution. Dates and times are always given in ISO 8601 format|
|date|string|The original date of the transaction as provided by the institution. Dates and times are always given in ISO 8601 format|
|amount|number|The original amount of the transaction as provided by the institution |
|currency|string (optional)|The currency of the transaction as provided by the institution, default AUD|
|status|string (optional)|The status of the transaction can be `POSTED` or `PENDING`|

# Using the Standard Service API

The required parameters for each file uploaded to the signed URL are listed below:

|   Name    |   Description |
|---|---|
|externalUserId: string|Your unique end-users, as defined by you|
|providerId: string|The bank or financial institution of the end-user. See GET `/api/providers` for a list of providers and their providerIDs|
|externalAccountId: string|The account number as provided by the bank or financial institution|
|accountType: string | The type of financial account as defined by the bank or financial institution, e.g. checking, savings, loan etc|
|externalTransactionId: string | The unique transaction number as defined by you, the bank or financial institution. Each transaction belongs to only one account.|
|type: string|A transaction type represents a money movement in or out of an account. CREDIT is money in, income etc.; DEBIT is money out, expense.|
|description: string |The original description of the transaction as provided by the institution i.e. as it appears in the original bank statement |
|date: string |The original date of the transaction as provided by the institution. Dates and times are always given in ISO 8601 format.|
|amount: number |The original amount of the transaction as provided by the institution. |
|currency: string (optional)|The currency of the transaction as provided by the institution, default AUD.|
|status: string (optional)|The status of the transaction can be POSTED or PENDING.|

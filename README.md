# Finch XP API Test Data

Testing the Finch XP APIs is simple and doesn't require you to use real transactional data thanks to our test data.

The Finch XP Test data consists of 100 transactions from fake users at 4 fake financial institutions/banks. You will have to specify the `productType` you are currently subscribed to in the request body.

You are welcome to test using your own real data although testing (both fake and real data) is limited to 1000 transactions, 100 users, or 90 days: whichever is first.

If you would like to test with your own data, please [contact us](mailto:sales@finchxp.com) and we’ll provide you with a list of financial institutions/banks that we support for testing.

To see a full list of all financial institutions/banks we support in production, check out our providers list [here](https://docs.finchxp.com).

# The Transaction Object

The required parameters for each transaction sent to the Finch XP APIs are listed below:

|   Name    |   Description |
|---|---|
|userId: string|Your unique end-users, as defined by you|
|providerId: string|The bank or financial institution of the end-user. See GET `/api/providers` for a list of providers and their providerIDs|
|accountNumber: string|The account number as provided by the bank or financial institution|
|accountType: string | The type of financial account as defined by the bank or financial institution, e.g. checking, savings, loan etc|
|transactionId: string | The unique transaction number as defined by you, the bank or financial institution. Each transaction belongs to only one account.|
|transactionType: string|A transaction type represents a money movement in or out of an account. CREDIT is money in, income etc.; DEBIT is money out, expense.|
|transactionDescription: string |The original description of the transaction as provided by the institution i.e. as it appears in the original bank statement |
|transactionDate: string |The original date of the transaction as provided by the institution. Dates and times are always given in ISO 8601 format.|
|transactionAmount: number |The original amount of the transaction as provided by the institution. |
|transactionCurrency: string (optional)|The currency of the transaction as provided by the institution, default AUD.|
|transactionStatus: string (optional)|The status of the transaction can be POSTED or PENDING.|

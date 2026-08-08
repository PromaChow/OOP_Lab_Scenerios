Design a program for a bank account management system with the following requirements:

Each **Account** has:

* A unique account number
* An owner name
* A balance
* A collection (ArrayList) of **Transaction** objects

Each **Transaction** records:

* An amount
* A label (e.g., deposit, withdrawal, failed withdrawal, interest)

The transaction list is stored inside the Account and represents its full history. Any deposit or withdrawal must create and append a Transaction entry instead of only modifying the balance.

There are three types of accounts, each with different rules:

**SavingsAccount**

* Earns interest using a tiered structure:

  * 2% interest on the portion of the balance up to 1000
  * 4% interest only on the portion above 1000
* Interest must be calculated in parts, not as a single flat rate

**CheckingAccount**

* Does not earn interest
* Allows overdraft up to a balance of -500
* Any withdrawal that would reduce the balance below -500 must:

  * Be rejected
  * Be recorded as a failed Transaction

**LoanAccount**

* Starts with a negative balance (representing money owed to the bank)
* Accepts deposits as loan repayments, with these rules:

  * Partial payments are allowed
  * A deposit must never make the balance positive
  * If a deposit exceeds the remaining loan, the balance is capped at zero
* Charges 6% interest on the outstanding (negative) balance, increasing the debt

Each Account must be able to:

* Apply monthly interest based on its specific rules
* Perform deposits and withdrawals with proper validation
* Record all actions as Transactions
* Display its details, including:

  * Account information
  * Current balance
  * Full transaction history

A **BankManager** class must:

* Store all accounts in an ArrayList
* Prevent duplicate account numbers
* Allow adding and removing accounts
* Apply monthly interest to all accounts at once
* Calculate the bank’s **total exposure**, defined as:

  * SavingsAccount and CheckingAccount balances are liabilities (money the bank owes customers)
  * LoanAccount balances (negative values) are assets (money owed to the bank)
  * The final exposure must reflect this difference, not just a simple sum

The program must demonstrate:

* At least five accounts across all three types
* At least one withdrawal that fails due to overdraft limits
* At least one LoanAccount deposit that is capped at zero instead of becoming positive
* Monthly interest applied to all accounts
* Output showing each account’s details and the bank’s total exposure


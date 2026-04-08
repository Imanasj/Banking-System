# Banking-System
This project implements a simple banking system in Java using inheritance, encapsulation, constructors, and method overriding.
The system includes a base  class, two specialized subclasses ( and ), and a  class to demonstrate how the accounts behave.

Project Structure


1. Base Class — BankAccount
Fields (private)
• 	
• 	
• 	
Constructor

• 	If  is negative → balance is set to .
Public Methods
• 	Getters:
, , 
• 	
• 	Ignores non‑positive amounts
• 	
• 	Returns  if amount ≤ 0
• 	Returns  if insufficient funds
• 	Otherwise subtracts and returns 
• 	
• 	Displays account number, owner, and balance

2. SavingsAccount (Subclass of BankAccount)
Additional Field
• 	 (annual %)
Constructor

• 	Calls 
• 	Negative interest rates are converted to 
Additional Methods
• 	Getter + setter for 
• 	Setter ignores negative values
• 	
• 	Monthly rate = 
• 	Interest = 
• 	Added using 
Overrides
• 	 → includes interest rate

3. CheckingAccount (Subclass of BankAccount)
Additional Fields
• 	 (must be ≤ 0)
• 	 (cannot be negative)
Constructor

• 	Calls 
• 	If overdraftLimit > 0 → converted to negative
• 	If transactionFee < 0 → set to 0
Overrides

• 	Ignores non‑positive amounts → returns 
• 	Calculates 
• 	If new balance < overdraftLimit → returns 
• 	Otherwise subtracts and returns 

• 	Includes overdraft limit and transaction fee

4. BankDemo (Test Class)
Inside 
Creates and tests two accounts:
SavingsAccount Test
1. 	Create:

2. 	Print initial state
3. 	Deposit 200
4. 	Withdraw 50
5. 	Apply monthly interest
6. 	Print final state
CheckingAccount Test
1. 	Create:

2. 	Print initial state
3. 	Withdraw 50
4. 	Withdraw 300
5. 	Withdraw 1000 (should fail)
6. 	Print final state

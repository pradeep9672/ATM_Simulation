1. Account Class
This class is the backbone of individual account management.
Attributes:
accountNumber, pin, and balance: These hold the account information and balance.
Methods:
validatePin(int enteredPin): Checks if the entered PIN matches the account’s PIN.
getBalance(): Returns the current balance of the account.
deposit(double amount): Increases the balance by the specified amount.
withdraw(double amount): Checks if the balance is sufficient, then deducts the specified amount if possible, returning true if successful and false otherwise.

2. ATM Class
Acts as a controller to manage multiple accounts and handle login operations.
Attributes:
HashMap<Integer, Account> accounts: Stores all accounts using account numbers as keys, making it easy to find accounts during login.
Methods:
login(int accountNumber, int pin): Validates the entered account number and PIN. If successful, it returns the corresponding Account object, or null if the login fails.
Purpose: This class is responsible for loading the account data and providing access control for account operations.

3. ATMGUI Class
The main GUI component, which extends JFrame (a Swing GUI window).
Attributes:

GUI components like JTextField, JPasswordField, and JButton for user input fields and actions.
currentAccount holds the logged-in user’s account data for session-specific operations.
Methods:
createLoginUI(): Displays the login screen with fields for entering the account number and PIN. Includes a Login button that calls handleLogin().
createATMUI(): Displays the main ATM menu (after successful login) with options for Deposit, Withdraw, and Check Balance.
handleLogin(): Reads account number and PIN from input fields, attempts login using the ATM class, and, if successful, displays the main ATM interface.
handleDeposit(): Reads the deposit amount, adds it to the balance, and updates the message with confirmation.
handleWithdraw(): Reads the withdrawal amount and checks if the balance is sufficient. If so, it deducts the amount and updates the message; otherwise, it shows an “Insufficient funds” message.
handleBalance(): Fetches and displays the current balance of the logged-in account.

5. Main GUI Workflow
When the application starts:

Login Screen: Users enter their account number and PIN. If they match an existing account in the ATM class, the main ATM screen opens.
Main ATM Screen: Users can deposit, withdraw, and check their balance.
Each action (deposit, withdraw, check balance) updates the display area to show the result or message.
Error Handling: For incorrect PIN or insufficient balance, messages provide feedback to guide the user.

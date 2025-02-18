# **🛠 ATM Simulator in C - Notes 📜**

## **1️⃣ Project Overview**
- This is a **basic ATM simulation** in C.
- The user can perform **3 main actions**:
  1. **Deposit money**
  2. **Withdraw money**
  3. **Check balance**
- The system ensures that withdrawals **do not exceed the available balance**.

---

## **2️⃣ Features**
✅ Initialize an account with a balance.  
✅ Allow deposits and update the balance.  
✅ Allow withdrawals only if funds are available.  
✅ Show the updated balance after each transaction.  
✅ Exit option to stop the program.  

---

## **3️⃣ C Code Implementation**
```c
#include <stdio.h>

// Function to display the menu
void displayMenu() {
    printf("\n🏧 ATM Simulator 🏧\n");
    printf("1️⃣ Deposit Money\n");
    printf("2️⃣ Withdraw Money\n");
    printf("3️⃣ Check Balance\n");
    printf("4️⃣ Exit\n");
    printf("Enter your choice: ");
}

int main() {
    int choice;
    float balance = 1000.00;  // Initial balance
    float amount;

    printf("\n💰 Welcome to the ATM Simulator! 💰\n");

    while (1) {
        displayMenu();
        scanf("%d", &choice);

        switch (choice) {
            case 1: // Deposit
                printf("💵 Enter amount to deposit: ");
                scanf("%f", &amount);
                if (amount > 0) {
                    balance += amount;
                    printf("✅ Successfully deposited ₹%.2f\n", amount);
                } else {
                    printf("❌ Invalid amount! Deposit must be greater than ₹0.\n");
                }
                break;

            case 2: // Withdraw
                printf("🏧 Enter amount to withdraw: ");
                scanf("%f", &amount);
                if (amount > 0 && amount <= balance) {
                    balance -= amount;
                    printf("✅ Successfully withdrawn ₹%.2f\n", amount);
                } else if (amount > balance) {
                    printf("❌ Insufficient balance! You only have ₹%.2f\n", balance);
                } else {
                    printf("❌ Invalid amount! Withdrawal must be greater than ₹0.\n");
                }
                break;

            case 3: // Check balance
                printf("💳 Your current balance: ₹%.2f\n", balance);
                break;

            case 4: // Exit
                printf("🚪 Exiting... Thank you for using the ATM!\n");
                return 0;

            default:
                printf("❌ Invalid choice! Please enter 1, 2, 3, or 4.\n");
        }
    }

    return 0;
}
```

---

## **4️⃣ Code Explanation**
### **🔹 Menu Display Function**
```c
void displayMenu() {
    printf("\n🏧 ATM Simulator 🏧\n");
    printf("1️⃣ Deposit Money\n");
    printf("2️⃣ Withdraw Money\n");
    printf("3️⃣ Check Balance\n");
    printf("4️⃣ Exit\n");
    printf("Enter your choice: ");
}
```
- Displays the available actions to the user.

### **🔹 Initializing Balance**
```c
float balance = 1000.00;
```
- The account starts with **₹1000.00**.

### **🔹 Deposit Money**
```c
printf("💵 Enter amount to deposit: ");
scanf("%f", &amount);
if (amount > 0) {
    balance += amount;
    printf("✅ Successfully deposited ₹%.2f\n", amount);
} else {
    printf("❌ Invalid amount! Deposit must be greater than ₹0.\n");
}
```
- Ensures deposit is **greater than ₹0**.
- Adds the deposit to the **balance**.

### **🔹 Withdraw Money**
```c
printf("🏧 Enter amount to withdraw: ");
scanf("%f", &amount);
if (amount > 0 && amount <= balance) {
    balance -= amount;
    printf("✅ Successfully withdrawn ₹%.2f\n", amount);
} else if (amount > balance) {
    printf("❌ Insufficient balance! You only have ₹%.2f\n", balance);
} else {
    printf("❌ Invalid amount! Withdrawal must be greater than ₹0.\n");
}
```
- Ensures withdrawal is **greater than ₹0**.
- Ensures withdrawal does **not exceed** the **available balance**.

### **🔹 Check Balance**
```c
printf("💳 Your current balance: ₹%.2f\n", balance);
```
- Displays the **current balance**.

### **🔹 Exit Option**
```c
printf("🚪 Exiting... Thank you for using the ATM!\n");
return 0;
```
- Ends the program.

---

## **5️⃣ Example Run**
```
💰 Welcome to the ATM Simulator! 💰

🏧 ATM Simulator 🏧
1️⃣ Deposit Money
2️⃣ Withdraw Money
3️⃣ Check Balance
4️⃣ Exit
Enter your choice: 1
💵 Enter amount to deposit: 500
✅ Successfully deposited ₹500.00

🏧 ATM Simulator 🏧
1️⃣ Deposit Money
2️⃣ Withdraw Money
3️⃣ Check Balance
4️⃣ Exit
Enter your choice: 3
💳 Your current balance: ₹1500.00

🏧 ATM Simulator 🏧
1️⃣ Deposit Money
2️⃣ Withdraw Money
3️⃣ Check Balance
4️⃣ Exit
Enter your choice: 2
🏧 Enter amount to withdraw: 2000
❌ Insufficient balance! You only have ₹1500.00

🏧 ATM Simulator 🏧
1️⃣ Deposit Money
2️⃣ Withdraw Money
3️⃣ Check Balance
4️⃣ Exit
Enter your choice: 4
🚪 Exiting... Thank you for using the ATM!
```

---

## **6️⃣ Enhancements You Can Add**
✅ Implement **PIN-based authentication** before accessing the ATM.  
✅ Store **transaction history** using file handling.  
✅ Add a **limit** on withdrawal (e.g., max ₹10,000 per transaction).  
✅ Allow **multiple users** with different balances.  

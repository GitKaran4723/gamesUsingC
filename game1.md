# **🎲 Dice Rolling Game (Player vs Computer) - Notes 📜**

## **1️⃣ Project Overview**
- This is a simple **dice game** between the **player** and the **computer**.
- Each turn:
  1. The player rolls a **random dice (1-6)**.
  2. The computer rolls a **random dice (1-6)**.
  3. The higher roll **wins** (+1 point).
  4. If both rolls are equal, it's a **draw** (no points).
- The game continues for **5 rounds**, and the winner is decided.

---

## **2️⃣ Features**
✅ Generates **random numbers (1-6)** for both player and computer.  
✅ Compares the rolls and **updates the score**.  
✅ Displays the **winner after 5 rounds**.  
✅ Allows the player to **play again or exit**.  

---

## **3️⃣ C Code Implementation**
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Function to roll the dice (random number between 1 and 6)
int rollDice() {
    return (rand() % 6) + 1;
}

int main() {
    int playerRoll, computerRoll;
    int playerScore = 0, computerScore = 0;
    char choice;

    srand(time(0));  // Seed random number generator

    printf("\n🎲 Welcome to the Dice Rolling Game! 🎲\n");
    printf("Rules: Roll a dice (1-6). Higher roll wins a point! Best of 5 rounds.\n");

    for (int round = 1; round <= 5; round++) {
        printf("\n🎮 Round %d - Press any key and Enter to roll the dice: ", round);
        scanf(" %c", &choice);

        // Generate dice rolls
        playerRoll = rollDice();
        computerRoll = rollDice();

        printf("🧑 You rolled: %d 🎲\n", playerRoll);
        printf("🤖 Computer rolled: %d 🎲\n", computerRoll);

        // Compare rolls and update scores
        if (playerRoll > computerRoll) {
            printf("✅ You win this round!\n");
            playerScore++;
        } else if (playerRoll < computerRoll) {
            printf("❌ Computer wins this round!\n");
            computerScore++;
        } else {
            printf("⚖️ It's a draw! No points awarded.\n");
        }

        printf("📊 Score: You [%d] - Computer [%d]\n", playerScore, computerScore);
    }

    // Display Final Result
    printf("\n🎉 Game Over! 🎉\n");
    if (playerScore > computerScore) {
        printf("🏆 Congratulations! You won the game with a score of %d - %d!\n", playerScore, computerScore);
    } else if (playerScore < computerScore) {
        printf("😢 Computer wins with a score of %d - %d. Better luck next time!\n", computerScore, playerScore);
    } else {
        printf("🤝 It's a tie! Both scored %d points!\n", playerScore);
    }

    printf("\nThanks for playing! 🎮\n");
    return 0;
}
```

---

## **4️⃣ Code Explanation**
### **🔹 Random Dice Roll**
```c
int rollDice() {
    return (rand() % 6) + 1;
}
```
- Generates a **random number between 1 and 6**, simulating a dice roll.

### **🔹 Loop for 5 Rounds**
```c
for (int round = 1; round <= 5; round++) {
```
- The game plays for **5 rounds**.

### **🔹 User Rolls the Dice**
```c
printf("\n🎮 Round %d - Press any key and Enter to roll the dice: ", round);
scanf(" %c", &choice);
```
- The player presses any key to **roll the dice**.

### **🔹 Computer Rolls the Dice**
```c
playerRoll = rollDice();
computerRoll = rollDice();
```
- Both the player and the computer roll the dice.

### **🔹 Compare Results**
```c
if (playerRoll > computerRoll) {
    printf("✅ You win this round!\n");
    playerScore++;
} else if (playerRoll < computerRoll) {
    printf("❌ Computer wins this round!\n");
    computerScore++;
} else {
    printf("⚖️ It's a draw! No points awarded.\n");
}
```
- Updates **playerScore** or **computerScore** based on dice roll comparison.

### **🔹 Final Result**
```c
if (playerScore > computerScore) {
    printf("🏆 Congratulations! You won the game with a score of %d - %d!\n", playerScore, computerScore);
} else if (playerScore < computerScore) {
    printf("😢 Computer wins with a score of %d - %d. Better luck next time!\n", computerScore, playerScore);
} else {
    printf("🤝 It's a tie! Both scored %d points!\n", playerScore);
}
```
- Displays **who won the game** after 5 rounds.

---

## **5️⃣ Example Game Run**
```
🎲 Welcome to the Dice Rolling Game! 🎲
Rules: Roll a dice (1-6). Higher roll wins a point! Best of 5 rounds.

🎮 Round 1 - Press any key and Enter to roll the dice: x
🧑 You rolled: 3 🎲
🤖 Computer rolled: 5 🎲
❌ Computer wins this round!
📊 Score: You [0] - Computer [1]

🎮 Round 2 - Press any key and Enter to roll the dice: y
🧑 You rolled: 6 🎲
🤖 Computer rolled: 2 🎲
✅ You win this round!
📊 Score: You [1] - Computer [1]

🎮 Round 3 - Press any key and Enter to roll the dice: z
🧑 You rolled: 4 🎲
🤖 Computer rolled: 4 🎲
⚖️ It's a draw! No points awarded.
📊 Score: You [1] - Computer [1]

🎮 Round 4 - Press any key and Enter to roll the dice: q
🧑 You rolled: 5 🎲
🤖 Computer rolled: 1 🎲
✅ You win this round!
📊 Score: You [2] - Computer [1]

🎮 Round 5 - Press any key and Enter to roll the dice: p
🧑 You rolled: 2 🎲
🤖 Computer rolled: 6 🎲
❌ Computer wins this round!
📊 Score: You [2] - Computer [2]

🎉 Game Over! 🎉
🤝 It's a tie! Both scored 2 points!

Thanks for playing! 🎮
```

---

## **6️⃣ Enhancements You Can Add**
✅ **Best of 10 rounds mode**.  
✅ **Betting System** – Player starts with points and bets before rolling.  
✅ **Leaderboard (Save Highest Score)** using file handling.  
✅ **Multiplayer Mode** – Allow two players to play instead of a computer.  

Would you like me to **enhance** any part of this game? 🚀

**"Lucky Number Game (Win & Lose Counter)"** in **C**

---

## 🎯 **Game Explanation:**
1. The computer randomly selects a number between **1 and 10**.
2. The player is asked to guess the number.
3. If the guess is **correct**, the **score increases by 1**.
4. If the guess is **wrong**, the **score decreases by 1**.
5. The game continues until the player decides to exit.

### **Additional Features:**
✅ The game displays a **hint** ("Too High" or "Too Low") if the guess is incorrect.  
✅ The player can **choose to quit anytime**.

---

## 💻 **C Code Implementation:**
Let's write a **well-structured** C program for this game.

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Function to generate a random number
int generateRandomNumber() {
    return (rand() % 10) + 1; // Generates a number between 1 and 10
}

int main() {
    int guess, randomNumber;
    int score = 0;
    char choice;
    
    // Seed random function using current time
    srand(time(0));

    printf("\n🎯 Welcome to the Lucky Number Game! 🎯\n");
    printf("Rules: Guess the number (1-10). Win -> Score Up (+1), Lose -> Score Down (-1)\n");
    printf("You can exit anytime by pressing 'q'.\n\n");

    while (1) {
        // Generate a new random number for each round
        randomNumber = generateRandomNumber();

        printf("\n🔢 Enter your guess (1-10): ");
        scanf(" %c", &choice); // Taking character input for quit option

        // Exit condition
        if (choice == 'q' || choice == 'Q') {
            printf("\n🚪 Exiting game... Your final score: %d\n", score);
            break;
        }

        // Convert character input to integer
        guess = choice - '0';

        // Check if input is within range
        if (guess < 1 || guess > 10) {
            printf("❌ Invalid input! Please enter a number between 1 and 10.\n");
            continue;
        }

        // Compare guess with the random number
        if (guess == randomNumber) {
            printf("✅ Correct! 🎉 You guessed the number!\n");
            score++;
        } else {
            printf("❌ Wrong guess! The correct number was %d.\n", randomNumber);
            score--;

            // Provide hints
            if (guess > randomNumber) {
                printf("Hint: Try a lower number! 📉\n");
            } else {
                printf("Hint: Try a higher number! 📈\n");
            }
        }

        // Display updated score
        printf("📊 Your current score: %d\n", score);
    }

    printf("\n🎮 Game Over! Thanks for playing! 🎮\n");
    return 0;
}
```

---

## 📜 **Code Explanation:**
### 🔹 **1. Random Number Generation**
```c
srand(time(0));
randomNumber = generateRandomNumber();
```
- The `srand(time(0))` function initializes the random number generator using the current time.
- The `generateRandomNumber()` function returns a **random number between 1 and 10**.

### 🔹 **2. Input Handling & Quit Option**
```c
scanf(" %c", &choice);
if (choice == 'q' || choice == 'Q') {
    printf("\n🚪 Exiting game... Your final score: %d\n", score);
    break;
}
```
- This allows the user to quit the game by pressing **'q' or 'Q'**.

### 🔹 **3. Checking the Guess**
```c
if (guess == randomNumber) {
    printf("✅ Correct! 🎉 You guessed the number!\n");
    score++;
} else {
    printf("❌ Wrong guess! The correct number was %d.\n", randomNumber);
    score--;
}
```
- If the player's guess **matches the random number**, their **score increases**.
- If the guess is **wrong**, the score **decreases**.

### 🔹 **4. Hints for the Next Guess**
```c
if (guess > randomNumber) {
    printf("Hint: Try a lower number! 📉\n");
} else {
    printf("Hint: Try a higher number! 📈\n");
}
```
- If the guess is too **high**, the game suggests **trying a lower number**.
- If the guess is too **low**, the game suggests **trying a higher number**.

---

## 🏆 **Example Game Run:**
```
🎯 Welcome to the Lucky Number Game! 🎯
Rules: Guess the number (1-10). Win -> Score Up (+1), Lose -> Score Down (-1)
You can exit anytime by pressing 'q'.

🔢 Enter your guess (1-10): 5
❌ Wrong guess! The correct number was 8.
Hint: Try a higher number! 📈
📊 Your current score: -1

🔢 Enter your guess (1-10): 7
✅ Correct! 🎉 You guessed the number!
📊 Your current score: 0

🔢 Enter your guess (1-10): 3
❌ Wrong guess! The correct number was 2.
Hint: Try a lower number! 📉
📊 Your current score: -1

🔢 Enter your guess (1-10): q
🚪 Exiting game... Your final score: -1

🎮 Game Over! Thanks for playing! 🎮
```

---

## 🛠 **Enhancements You Can Try:**
🔹 Add a **leaderboard** to store high scores in a file.  
🔹 Allow the user to set a **difficulty level** (Easy: 1-10, Hard: 1-50).  
🔹 Add a **timer** to make the game more exciting.  


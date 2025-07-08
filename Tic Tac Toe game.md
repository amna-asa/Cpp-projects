# 🎮 Tic Tac Toe Game in C++

This is a simple **Tic Tac Toe** game implemented in **C++** using basic concepts such as:

- 2D arrays
- Conditional statements
- Functions
- Input/output handling
- Recursion for repeated actions

The game supports **two players** taking alternate turns by entering a number from 1 to 9 corresponding to a position on the 3×3 grid.

## 🧩 Game Features

- Displays a 3×3 board
- Allows players to choose their moves using number keys
- Detects invalid or already-taken spots
- Checks for winning conditions (rows, columns)
- Declares a winner or a tie after all moves

## ▶️ How to Play

1. Player 1 uses `'x'` and Player 2 uses `'o'`.
2. Input a number from **1 to 9** to place your symbol on the board.
3. Game will automatically alternate between players.
4. The board updates after every move, and a winner is declared if a row/column is filled with the same symbol.

## 🖼️ Game Screenshots

> Below are some snapshots of the game in action:

### Initial Setup
![A](/C++%20images/1.PNG)

### Mid-game Board
![A](/C++%20images/2.PNG)

### Game End or Win Screen
![A](/C++%20images/3.PNG)

```C++

#include <iostream>
using namespace std;

//setpup
//menu
//actions
//winner parameters

int turn;
char player1 = 'x';
char player2 = 'o';

char board[3][3] = {
    {'1', '2', '3'},
    {'4', '5', '6'},
    {'7', '8', '9'}
};

void setup() {
    cout << "\n";
    cout << " " << board[0][0] << " | " << board[0][1] << " | " << board[0][2] << endl;
    cout << "---|---|---" << endl;
    cout << " " << board[1][0] << " | " << board[1][1] << " | " << board[1][2] << endl;
    cout << "---|---|---" << endl;
    cout << " " << board[2][0] << " | " << board[2][1] << " | " << board[2][2] << endl;
    cout << "\n";
}

void x_actions() {
    cout << "PLAYER 1 (x), enter the place (1-9): ";
    cin >> turn;

    int position = turn - 1;  
    int row = position / 3;   
    int col = position % 3; 

    if (board[row][col] != 'x' && board[row][col] != 'o') {
        board[row][col] = 'x';
    }
    else {
        cout << "That spot is already taken! Try again." << endl;
        x_actions();
        return;
    }

    setup();
}

void o_actions() {
    cout << "PLAYER 2 (o), enter the place (1-9): ";
    cin >> turn;

    int position = turn - 1;
    int row = position / 3;
    int col = position % 3;

    if (board[row][col] != 'x' && board[row][col] != 'o') {
        board[row][col] = 'o';
    }
    else {
        cout << "That spot is already taken! Try again." << endl;
        o_actions();
        return;
    }

    setup();
}

char checkWinner() {
    for (int i = 0; i < 3; i++) {
        if (board[i][0] == board[i][1] && board[i][1] == board[i][2])
            return board[i][0];
        if (board[0][i] == board[1][i] && board[1][i] == board[2][i])
            return board[0][i];
    }
    return ' ';
}

int main() {
    cout << "---------------WELCOME TO TIC TAC TOE GAME-----------------\n" << endl;

    setup();

    cout << "RULES:\n";
    cout << "1. 'x' is Player 1 and 'o' is Player 2\n";
    cout << "2. On your turn, enter a number (1 to 9) to place your symbol\n";
    cout << "Press ENTER to start..." << endl;
    system("pause");
    system("cls");

    char winner = ' ';
    for (int i = 0; i < 9; i++) {
        if (i % 2 == 0) {
            x_actions();
        }
        else {
            o_actions();
        }

        winner = checkWinner();
        if (winner == 'x') {
            cout << "PLAYER 1 (x) WINS!" << endl;
            break;
        }
        else if (winner == 'o') {
            cout << "PLAYER 2 (o) WINS!" << endl;
            break;
        }
    }

    if (winner == ' ') {
        cout << "It's a TIE!" << endl;
    }

    return 0;
}


```



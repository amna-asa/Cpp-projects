# **TaskMate**
*A Console-Based Task Manager with User Authentication*

---

## 📌 Project Overview
**TaskMate** is a C++ console application that allows multiple users to manage their daily tasks after logging in. Each user has a personalized task list saved in a separate file. It combines file handling, user authentication, and structured data display using standard C++ libraries.

---

## 🔐 User Management
- Users can **Sign Up** or **Log In** using a username and password.  
- Validates uniqueness and enforces usernames with digits or special characters.  
- Stores credentials in a text file: `users.txt`.

---

## 📂 Task Management Features
Each user can perform the following actions:

- **Add Task**  
  Input task title, description, priority, and due date.

- **Display Tasks**  
  Shows tasks in a formatted table (No., Title, Date, Priority).

- **Edit Task**  
  Options to update:
  - Title  
  - Description  
  - Priority  
  - Date  
  - Or mark a task as completed (which deletes it).

---

## 💾 Data Storage
- User credentials → `users.txt`  
- Tasks → `<username>_tasks.txt`  
- File handling is done using `ifstream` and `ofstream`.

---

## ⚙️ Technologies Used
- **Language:** C++  
- **Libraries:**  
  - `<iostream>`, `<fstream>` – Input/Output and File Handling  
  - `<vector>` – Dynamic list of tasks  
  - `<string>`, `<iomanip>`, `<cctype>` – String operations and formatting

---

## 🧪 Example Flow
1. User opens program → signs up or logs in  
2. Loads their existing tasks (if any)  
3. Can add, view, or modify tasks  
4. All changes saved to file on exit

---
![A](/C++%20images/1.PNG)

---

![A](/C++%20images/2.PNG)

---

![A](/C++%20images/3.PNG)

---

![A](/C++%20images/4.PNG)


```
#include <iostream>
#include <fstream>
#include <vector>
#include <string>
#include <iomanip>
#include <cctype>

using namespace std;

struct Task {
    string title;
    string description;
    int priority;
    int day, month, year;
};

class TaskBoard {
private:
    vector<Task> tasks;

public:
    void loadTasks(const string& filename) {
        tasks.clear();
        ifstream file(filename);
        Task task;
        while (getline(file, task.title) &&
            getline(file, task.description) &&
            file >> task.priority >> task.day >> task.month >> task.year) {
            file.ignore();
            tasks.push_back(task);
        }
        file.close();
    }

    void saveTasks(const string& filename) {
        ofstream file(filename);
        for (const Task& task : tasks) {
            file << task.title << "\n"
                << task.description << "\n"
                << task.priority << " " << task.day << " " << task.month << " " << task.year << "\n";
        }
        file.close();
    }

    void addTask() {
        Task task;
        cin.ignore();
        cout << "Enter titl (title must be of 20 words): ";
        getline(cin, task.title);
        cout << "Enter description: ";
        getline(cin, task.description);
        cout << "Enter priority: ";
        cin >> task.priority;
        cout << "Enter day: ";
        cin >> task.day;
        cout << "Enter month: ";
        cin >> task.month;
        cout << "Enter year: ";
        cin >> task.year;
        tasks.push_back(task);
        cout << "Task added successfully.\n";
    }

    void displayTasks() {
        cout << left << setw(5) << "No." << setw(25) << "Title" << setw(12) << "Date" << setw(8) << "Priority" << endl;
        cout << "-------------------------------------------------------------\n";
        for (int i = 0; i < tasks.size(); ++i) {
            cout << left << setw(5) << (i + 1)
                << setw(25) << tasks[i].title
                << setw(2) << tasks[i].day << "/"
                << setw(2) << tasks[i].month << "/"
                << setw(6) << tasks[i].year
                << setw(8) << tasks[i].priority
                << endl;
        }
    }

    void editTask() {
        displayTasks();
        int index;
        cout << "Enter the task number to edit: ";
        cin >> index;
        if (index < 1 || index > tasks.size()) {
            cout << "Invalid task number.\n";
            return;
        }

        Task& task = tasks[index - 1];
        int choice;
        cout << "What do you want to edit?\n";
        cout << "1. Title\n2. Description\n3. Priority\n4. Date\n5. Mark as Completed\n";
        cin >> choice;
        cin.ignore();

        switch (choice) {
        case 1:
            cout << "Enter new title: ";
            getline(cin, task.title);
            break;
        case 2:
            cout << "Enter new description: ";
            getline(cin, task.description);
            break;
        case 3:
            cout << "Enter new priority: ";
            cin >> task.priority;
            break;
        case 4:
            cout << "Enter new day: ";
            cin >> task.day;
            cout << "Enter new month: ";
            cin >> task.month;
            cout << "Enter new year: ";
            cin >> task.year;
            break;
        case 5: {
            int status;
            cout << "Is the task completed? (1 for Yes, 2 for No): ";
            cin >> status;
            if (status == 1) {
                tasks.erase(tasks.begin() + index - 1);
                cout << "Task marked as completed and deleted.\n";
            }
            else {
                cout << "Task not completed yet.\n";
            }
            break;
        }
        default:
            cout << "Invalid choice.\n";
            return;
        }
    }
};

class UserManager {
private:
    string currentUser;

public:
    bool login(const string& username, const string& password) {
        ifstream file("users.txt");
        string u, p;
        while (file >> u >> p) {
            if (u == username && p == password) {
                currentUser = username;
                return true;
            }
        }
        return false;
    }

    void signup(const string& username, const string& password) {
        ofstream file("users.txt", ios::app);
        file << username << " " << password << "\n";
    }

    string getTaskFilename() const {
        return currentUser + "_tasks.txt";
    }
};

// ========================
// Helper Functions
// ========================

bool isUsernameTaken(const string& username) {
    ifstream file("users.txt");
    string u, p;
    while (file >> u >> p) {
        if (u == username)
            return true;
    }
    return false;
}

bool containsDigitOrSpecial(const string& str) {
    for (char c : str) {
        if (isdigit(c) || ispunct(c))
            return true;
    }
    return false;
}

vector<string> suggestUsernames(const string& base) {
    return { base + "123", base + "_01", base + "@", base + "99" };
}

// ========================
// Title Display
// ========================

void display() {
    int consoleWidth = 100;
    string lines[] = {
        "  ______ ___    _____  __ __    __  ___ ___   ______ ______",
        " /_  __//   |  / ___/ / //_/   /  |/  //   | /_  __// ____/",
        "  / /  / /| |  \\__ \\ / ,<     / /|_/ // /| |  / /  / __/   ",
        " / /  / ___ | ___/ // /| |   / /  / // ___ | / /  / /___   ",
        "/_/  /_/  |_|/____//_/ |_|  /_/  /_//_/  |_|/_/  /_____/   "
    };

    for (const string& line : lines) {
        int padding = (consoleWidth - line.length()) / 2;
        cout << string(padding, ' ') << line << endl;
    }
}

// ========================
// MAIN
// ========================

int main() {
    display();
    cout << endl << endl;
    UserManager userManager;
    TaskBoard taskBoard;
    int choice;
    string username, password;

    while (true) {
        cout << "\n1. Login\n2. Signup\n3. Exit\nChoose: ";
        cin >> choice;
        if (choice == 1) {
            cout << "Enter username: ";
            cin >> username;
            cout << "Enter password: ";
            cin >> password;
            if (userManager.login(username, password)) {
                cout << "Login successful!\n";
                break;
            }
            else {
                cout << "Invalid credentials.\n";
            }
        }
        else if (choice == 2) {
            cout << "Choose username: ";
            cin >> username;

            if (isUsernameTaken(username)) {
                cout << "This username is already taken.\n";
                cout << "Here are some suggestions:\n";
                for (const string& suggestion : suggestUsernames(username)) {
                    cout << " - " << suggestion << endl;
                }
                continue;
            }

            if (!containsDigitOrSpecial(username)) {
                cout << " Your username must include at least one number or special character.\n";
                cout << "Here are some better suggestions:\n";
                for (const string& suggestion : suggestUsernames(username)) {
                    cout << " - " << suggestion << endl;
                }
                continue;
            }

            cout << "Choose password: ";
            cin >> password;
            userManager.signup(username, password);
            cout << "Signup successful! You can now login.\n";
        }
        else if (choice == 3) {
            return 0;
        }
        else {
            cout << "Invalid option.\n";
        }
    }

    system("cls");
    display();
    cout << endl << endl;

    string filename = userManager.getTaskFilename();
    taskBoard.loadTasks(filename);

    while (true) {
        cout << "\n1. Add Task\n2. Display Tasks\n3. Edit Task\n4. Exit\nChoose: ";
        cin >> choice;
        switch (choice) {
        case 1:
            taskBoard.addTask();
            taskBoard.saveTasks(filename);
            system("cls");
            display();
            cout << endl << endl;
            break;
        case 2:
            taskBoard.displayTasks();
            break;
        case 3:
            taskBoard.editTask();
            taskBoard.saveTasks(filename);
            system("cls");
            display();
            cout << endl << endl;
            break;
        case 4:
            taskBoard.saveTasks(filename);
            system("cls");
            display();
            cout << endl << endl;
            return 0;
        default:
            cout << "Invalid option.\n";
            system("cls");
            display();
            cout << endl << endl;
        }
    }
}
```

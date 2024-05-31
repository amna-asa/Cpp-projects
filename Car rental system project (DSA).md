# Car rental syatem 
 
This C++ application is a car rental system that allows users to select a car from a list of available car companies, input their personal information, make a booking, and receive a total cost for the rental period. Additionally, the system offers a currency exchange service for international users. 

## Factors 

Following are the factors in this code:
- Car company's selection
- Selection of type of cars(luxury or campact)
- It will display the specifications of that car 
- Then it will ask for customer's data(name, age, address, driving licence number, contact number, email, CNIC)
- After that it will ask for the number of days customer want to book car 
- It will calculate money
- Then it will display the currency exchange policy note and ask for weather or not customer want to avail that policy or not
- If selected yes then it will give some currencies that customer want to select
- Then according to that currency it will display amount 
- At last it will display a receipt.

## Demonstrating Car Rental System Outputs with Explanations

So, here are the explanation of working or code along with the screen shots of output.

### Company selection page

![A](/C++%20images/Capture1.PNG)
### Car class selection

![B](/C++%20images//Capture2.PNG)

### Car specification 

![C](/C++%20images//Capture3.PNG)

### Customer data entry

![D](/C++%20images//Capture4.PNG)

### Booking according to number of days

![E](/C++%20images//Capture5.PNG)

### Bill in pak rupee display

![F](/C++%20images//Capture6.PNG)

### Currency exchange policy note

![G](/C++%20images//Capture7.PNG)

### Selection of currency and bill display if selected yes

![H](/C++%20images//Capture8.PNG)

### Receipt display

![I](/C++%20images//Capture9.PNG)


##  Project code

```C++

#include<iostream>
#include<string>
#include <iomanip>
#include <fstream>
using namespace std;

int c, a;
string n, ad, gm, e, pn, ln, ag, cnic;
string b, d;
double f, t, y;
double cr, x;
int k;
class  Node {
public:

	string data;
	Node* left;
	Node* right;
};
void selection()
{

	cout << "\t\t\t\tSelect the following car companies" << endl;
	cout << "\t\t\t\t 1. Tesla " << endl;
	cout << "\t\t\t\t 2. BMW " << endl;
	cout << "\t\t\t\t 3. Audi " << endl;
	cout << "\t\t\t\t 4. Ferrari " << endl;
	cout << "\t\t\t\t 5. Mercedes " << endl;
	cout << endl;
	cout << "\t\t\t\t                  _____________________________________________" << endl;
	cout << endl;
	cout << "Enter '1' for Tesla" << endl;
	cout << "Enter '2' for BMW" << endl;
	cout << "Enter '3' for Audi" << endl;
	cout << "Enter '4' for Ferrari" << endl;
	cout << "Enter '5' for Mercedes" << endl;

	cout << endl;

	cin >> c;
	cin.ignore();
	if (c == 1)
	{
		Node* root = new Node();
		Node* node2 = new Node();
		Node* node3 = new Node();
		Node* node4 = new Node();
		Node* node5 = new Node();
		Node* node6 = new Node();
		Node* node7 = new Node();

		root->data = "Tesla";
		node2->data = "Luxirious";
		node3->data = "Compact";

		node4->data = "Tesla Model S";
		node5->data = "Tesla Model X";

		node6->data = "Tesla Model 3";
		node7->data = "Tesla Model Y";

		root->left = node2;
		root->right = node3;
		node2->left = node4;
		node2->right = node5;
		node3->left = node6;
		node3->right = node7;

		cout << "              " << root->data << endl;
		cout << endl;

		cout << "Which kind of cars do you want ' Luxurious or Compact'  ? " << endl << endl;
		cout << "Enter 1 for Luxurious" << endl;
		cout << "Enter 2 for Compact" << endl << endl;
		cin >> a;
		cin.ignore();
		cout << endl;
		if (a == 1)
		{
			cout << " - " << root->left->data << endl;
			cout << " -> " << root->left->left->data << endl;
			cout << " -> " << root->left->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl << endl;
			cout << " - 1 for Tesla Model S" << endl;
			cout << " - 2 forTesla Model X " << endl << endl;
			cin >> k;
			cin.ignore();
		}
		else if (a == 2)
		{
			cout << " - " << root->right->data << endl;
			cout << " -> " << root->right->left->data << endl;
			cout << " -> " << root->right->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl << endl;
			cout << " - 1 for Tesla Model 3" << endl;
			cout << " - 2 forTesla Model Y " << endl << endl;
			cin >> k;
			cin.ignore();
		}
		else
		{
			cout << "ERROR *_*" << endl;
		}
		cout << endl;
	}
	else if (c == 2)
	{
		Node* root = new Node();
		Node* node2 = new Node();
		Node* node3 = new Node();
		Node* node4 = new Node();
		Node* node5 = new Node();
		Node* node6 = new Node();
		Node* node7 = new Node();

		root->data = "BMW";
		node2->data = "Luxirious";
		node3->data = "Compact";

		node4->data = "BMW 7 series";
		node5->data = "BMW X 7";

		node6->data = "BMW 3 series";
		node7->data = "BMW  X 1";

		root->left = node2;
		root->right = node3;
		node2->left = node4;
		node2->right = node5;
		node3->left = node6;
		node3->right = node7;

		cout << "              " << root->data << endl;
		cout << endl;

		cout << "Which kind of cars do you want ' Luxurious or Compact'  ? " << endl << endl;
		cout << "Enter 1 for Luxurious" << endl;
		cout << "Enter 2 for Compact" << endl << endl;
		cin >> a;
		cin.ignore();
		cout << endl;
		if (a == 1)
		{
			cout << " - " << root->left->data << endl;
			cout << " -> " << root->left->left->data << endl;
			cout << " -> " << root->left->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl << endl;
			cout << " - 1 for BMW 7 series" << endl;
			cout << " - 2 for BMW X 7 " << endl << endl;
			cin >> k;
			cin.ignore();
		}
		else if (a == 2)
		{
			cout << " - " << root->right->data << endl;
			cout << " -> " << root->right->left->data << endl;
			cout << " -> " << root->right->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl;
			cout << " - 1 for BMW 3 series" << endl;
			cout << " - 2 for BMW X 1 " << endl;
			cin >> k;
			cin.ignore();
		}
		else
		{
			cout << "ERROR *_*" << endl;
		}

		cout << endl;

	}
	else if (c == 3)
	{
		Node* root = new Node();
		Node* node2 = new Node();
		Node* node3 = new Node();
		Node* node4 = new Node();
		Node* node5 = new Node();
		Node* node6 = new Node();
		Node* node7 = new Node();

		root->data = "Audi";
		node2->data = "Luxirious";
		node3->data = "Compact";

		node4->data = "Audi A8";
		node5->data = "Audi Q8";

		node6->data = "Audi A3";
		node7->data = "Audi Q3";

		root->left = node2;
		root->right = node3;
		node2->left = node4;
		node2->right = node5;
		node3->left = node6;
		node3->right = node7;

		cout << "              " << root->data << endl;
		cout << endl;

		cout << "Which kind of cars do you want ' Luxurious or Compact'  ? " << endl;
		cout << "Enter 1 for Luxurious" << endl;
		cout << "Enter 2 for Compact" << endl;
		cin >> a;
		cin.ignore();
		cout << endl;
		if (a == 1)
		{
			cout << " - " << root->left->data << endl;
			cout << " -> " << root->left->left->data << endl;
			cout << " -> " << root->left->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl;
			cout << " - 1 for Audi A8" << endl;
			cout << " - 2 for Audi Q8 " << endl;
			cin >> k;
			cin.ignore();
		}
		else if (a == 2)
		{
			cout << " - " << root->right->data << endl;
			cout << " -> " << root->right->left->data << endl;
			cout << " -> " << root->right->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl;
			cout << " - 1 for Audi A 3" << endl;
			cout << " - 2 for Audi Q3 " << endl;
			cin >> k;
			cin.ignore();
		}
		else
		{
			cout << "ERROR *_*" << endl;
		}

		cout << endl;

	}
	else if (c == 4)
	{
		Node* root = new Node();
		Node* node2 = new Node();
		Node* node3 = new Node();
		Node* node4 = new Node();
		Node* node5 = new Node();
		Node* node6 = new Node();
		Node* node7 = new Node();

		root->data = "Ferrari";
		node2->data = "Luxirious";
		node3->data = "Compact";

		node4->data = "Ferrari 488 GTB";
		node5->data = "Ferrari Portofin";

		node6->data = "Ferrari F8 Tributo";
		node7->data = "Ferrari Roma";

		root->left = node2;
		root->right = node3;
		node2->left = node4;
		node2->right = node5;
		node3->left = node6;
		node3->right = node7;

		cout << "              " << root->data << endl;
		cout << endl;

		cout << "Which kind of cars do you want ' Luxurious or Compact'  ? " << endl;
		cout << "Enter 1 for Luxurious" << endl;
		cout << "Enter 2 for Compact" << endl;
		cin >> a;
		cin.ignore();
		cout << endl;
		if (a == 1)
		{
			cout << " - " << root->left->data << endl;
			cout << " -> " << root->left->left->data << endl;
			cout << " -> " << root->left->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl;
			cout << " - 1 for Ferrari 488 GTB" << endl;
			cout << " - 2 for Ferrari Portfino" << endl;
			cin >> k;
			cin.ignore();
		}
		else if (a == 2)
		{
			cout << " - " << root->right->data << endl;
			cout << " -> " << root->right->left->data << endl;
			cout << " -> " << root->right->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl;
			cout << " - 1 for Ferrari F 8 Tributo" << endl;
			cout << " - 2 for Ferrari Roma " << endl;
			cin >> k;
			cin.ignore();
		}
		else
		{
			cout << "ERROR *_*" << endl;
		}

		cout << endl;

	}
	else if (c == 5)
	{
		Node* root = new Node();
		Node* node2 = new Node();
		Node* node3 = new Node();
		Node* node4 = new Node();
		Node* node5 = new Node();
		Node* node6 = new Node();
		Node* node7 = new Node();

		root->data = "Mercedes";
		node2->data = "Luxirious";
		node3->data = "Compact";

		node4->data = "Mercedes-Benz S-class";
		node5->data = "Mercedes-Benx GLE";

		node6->data = "Mercedes-Bnez A-class";
		node7->data = "Mercedes-Benz GLA";

		root->left = node2;
		root->right = node3;
		node2->left = node4;
		node2->right = node5;
		node3->left = node6;
		node3->right = node7;

		cout << "              " << root->data << endl;
		cout << endl;
		cout << endl;
		cout << "Which kind of cars do you want ' Luxurious or Compact'  ? " << endl;
		cout << "Enter 1 for Luxurious" << endl;
		cout << "Enter 2 for Compact" << endl;
		cin >> a;
		cin.ignore();
		cout << endl;
		if (a == 1)
		{
			cout << " - " << root->left->data << endl;
			cout << " -> " << root->left->left->data << endl;
			cout << " -> " << root->left->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl;
			cout << " - 1 for Mercedes-Benz S-class" << endl;
			cout << " - 2 for Mercedes-Benz GLE" << endl;
			cin >> k;
			cin.ignore();
		}
		else if (a == 2)
		{
			cout << " - " << root->right->data << endl;
			cout << " -> " << root->right->left->data << endl;
			cout << " -> " << root->right->right->data << endl;
			cout << endl;
			cout << "Enter following keys for specific car " << endl;
			cout << " - 1 for Mercedes-Benz A-class" << endl;
			cout << " - 2 for Mercedes-Benz GLA" << endl;
			cin >> k;
			cin.ignore();
		}
		else
		{
			cout << "ERROR *_*" << endl;
		}

		cout << endl;

	}
	else
	{
		cout << endl;
		cout << "ERROR *_*" << endl;
	}

	cout << "Selected Car: ";
	if (c == 1 && a == 1 && k == 1)
	{
		cout << "Tesla Model S" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Range:           " << " Up to 360 miles (579 km)" << endl;
		cout << "-" << " Acceleration:    " << " 0-60 mph (0-97 km/h) in 2.5 seconds (Plaid version)" << endl;
		cout << "-" << " Top Speed:        " << " 155 mph (250 km/h)" << endl;
		cout << "-" << " Seating:         " << " 4-5 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,508 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}//tesla1
	else if (c == 1 && a == 1 && k == 2)
	{
		cout << "Tesla Model X" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " Inline-6, V8" << endl;
		cout << "-" << " Seating:         " << " 7 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 68 cu ft (1,926 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 1 && a == 2 && k == 1)
	{
		cout << "Tesla Model 3" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Range:           " << "  Up to 353 miles (568 km)" << endl;
		cout << "-" << " Acceleration:    " << " 0-60 mph (0-97 km/h) in 3.1 seconds (Performance version)" << endl;
		cout << "-" << " Top Speed:        " << " 162 mph (260 km/h)" << endl;
		cout << "-" << " Seating:         " << " 5 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 15 cu ft (425 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 1 && a == 2 && k == 2)
	{
		cout << "Tesla Model Y" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Range:           " << " Up to 326 miles (525 km)" << endl;
		cout << "-" << " Acceleration:    " << " 0-60 mph (0-97 km/h) in 3.5 seconds (Performance version)" << endl;
		cout << "-" << " Top Speed:        " << " 150 mph (241 km/h)" << endl;
		cout << "-" << " Seating:         " << " 5-6 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 68 cu ft (1,926 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}

	else if (c == 2 && a == 1 && k == 1)
	{
		cout << "BMW 7 Series" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " Inline-4, Inline-6" << endl;
		cout << "-" << " Seating:         " << " 4 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 98 cu ft (1,926 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 2 && a == 1 && k == 2)
	{
		cout << "  BMW X 7 " << endl << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " Inline-4, Inline-6" << endl;
		cout << "-" << " Seating:         " << " 4 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 98 cu ft (1,926 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 2 && a == 2 && k == 1)
	{
		cout << "BMW M3" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " Inline-4" << endl;
		cout << "-" << " Seating:         " << " 4 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 98 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 2 && a == 2 && k == 2)
	{
		cout << "  BMW X 1 " << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " Inline-4" << endl;
		cout << "-" << " Seating:         " << " 4 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 98 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}

	else if (c == 3 && a == 1 && k == 1)
	{
		cout << "Audi R8" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " 3.9-liter twin-turbocharged V8" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 3 && a == 1 && k == 2)
	{
		cout << "  Audi Q8 " << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " 3.9-liter twin-turbocharged V8" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 3 && a == 2 && k == 1)
	{
		cout << " Audi A 3" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " 3.9-liter twin-turbocharged V8" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 3 && a == 2 && k == 2)
	{
		cout << "  Audi A 3" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " 3.9-liter twin-turbocharged V8" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
		}

	else if (c == 4 && a == 1 && k == 1)
	{
		cout << "Ferrari Portofino" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " 3.9-liter twin-turbocharged V8" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 4 && a == 1 && k == 2)
	{
		cout << "  Ferrari F 8 Tributo" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " 3.9-liter twin-turbocharged V8" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 4 && a == 2 && k == 1)
	{
		cout << "Ferrari F8 Spider" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " 3.9-liter twin-turbocharged V8" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 4 && a == 2 && k == 2)
	{
		cout << "  Ferrari Roma " << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " 3.9-liter twin-turbocharged V8" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}

	else if (c == 5 && a == 1 && k == 1)
	{
		cout << "Mercedes S-Class" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " V6, V8, V12" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (a == 5 && a == 1 && k == 2)
	{
		cout << "  Mercedes-Benz S-class" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " V6, V8, V12" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 5 && a == 2 && k == 1)
	{
		cout << "Mercedes AMG GT" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " V6, V8, V12" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else if (c == 5 && a == 2 && k == 2)
	{
		cout << " Mercedes-Benz GLE" << endl;
		cout << " SPECIFICATIONS :" << endl << endl << endl;

		cout << "-" << " Engine:          " << " V6, V8, V12" << endl;
		cout << "-" << " Seating:         " << " 2 passengers" << endl;
		cout << "-" << " Cargo Capacity:  " << " 88 cu ft (2,7826 liters)" << endl;
		cout << "-" << " Battery:         " << " Various options available" << endl;
	}
	else
	{
		cout << "  Come later " << endl;
		cout << "   OR " << endl;
		cout << " Chose another" << endl;
	}
}
void information()
{
	ofstream outputFile("data.txt", ios::app); // Open the file in append mode

	if (!outputFile) {
		cout << "Error opening file!" << endl;
		return;
	}


	cout << "Full name: ";
	getline(cin, n);

	cout << "Age: ";
	getline(cin, ag);

	cout << "Licence number: ";
	getline(cin, ln);

	cout << "G-Mail: ";
	getline(cin, gm);

	cout << "Address: ";
	getline(cin, ad);

	cout << "Contact number: ";
	getline(cin, pn);

	cout << "CNIC: ";
	getline(cin, cnic);

	// Write the data to the file
	outputFile << "Full Name: " << n << endl;
	outputFile << "Age: " << ag << endl;
	outputFile << "Licence Number: " << ln << endl;
	outputFile << "G-Mail: " << gm << endl;
	outputFile << "Address: " << ad << endl;
	outputFile << "Contact Number: " << pn << endl;
	outputFile << "CNIC: " << cnic << endl;

	outputFile.close(); // Close the file
}
void booking() {

	cout << "When do you want to make the booking?  " << endl;
	cout << " - Enter '1' for booking now" << endl << " - Enter '2' for later \ Advance booking   " << endl;
	getline(cin, d);
}
void rate()
{
	cout << "_______________________________________________________ " << endl;
	cout << "|Per day coast of single car rent if  '5000' pk rupees |" << endl;
	cout << "|______________________________________________________| " << endl;
	cout << endl;
	cout << "For how many number of days do you want car on rent ? " << endl;
	cout << endl;
	cout << "Enter only the number of days in digits !  : ";
	cin >> f;
	cin.ignore();

	t = 5000 * f;
	cout << endl;
	cout << "Your total bill for " << f << " days will be " << t << " Rs" << endl;
}
void choice()
{
	cout << "   _________    ____       ____  _______   ___________    __       _______  _____________________  ___" << endl;
	cout << "  / ____/   |  / __ \\     / __ \\/ ____/ | / /_  __/   |  / /      / ___/\\ \\/ / ___/_  __/ ____/  |/  /" << endl;
	cout << " / /   / /| | / /_/ /    / /_/ / __/ /  |/ / / / / /| | / /       \\__ \\  \\  /\\__ \\ / / / __/ / /|_/ /" << endl;
	cout << "/ /___/ ___ |/ _, _/    / _, _/ /___/ /|  / / / / ___ |/ /___    ___/ /  / /___/ // / / /___/ /  / /" << endl;
	cout << "\\____/_/  |_/_/ |_|    /_/ |_|\\_____/_/ |_/ /_/ /_/  |_/_____/   /____/  /_//____//_/ /_____/_/  /_/" << endl;
	cout << endl << endl;
	cout << "--------------------------------------* WELCOME TO OUR CAR RENTAL SYSTEM *----------------------------------------" << endl;
	cout << endl;
	cout << endl;
	cout << "          -OUR CURRENCY EXCHANGE POLICY-" << endl;
	cout << endl;
	cout << " *  We are also provind a service of currency exchange " << endl;
	cout << " * If you are a foreigner in Pakistan then, it will be very helpful for you " << endl;
	cout << " * We have currency exchange for the following curriencies : " << endl;
	cout << "        - USD" << endl;
	cout << "        - Dinar" << endl;
	cout << "        - Euro" << endl;
	cout << "        - Pound" << endl;
	cout << "        - Rayal" << endl;
	cout << "________________________________________________" << endl;
	cout << endl;
	cout << "If you want to avail this facility then press '1'  if you want to pay in pak rupee then press '2'" << endl;
	cin >> y;
	cin.ignore();
	system("cls");
	cout << "   _________    ____       ____  _______   ___________    __       _______  _____________________  ___" << endl;
	cout << "  / ____/   |  / __ \\     / __ \\/ ____/ | / /_  __/   |  / /      / ___/\\ \\/ / ___/_  __/ ____/  |/  /" << endl;
	cout << " / /   / /| | / /_/ /    / /_/ / __/ /  |/ / / / / /| | / /       \\__ \\  \\  /\\__ \\ / / / __/ / /|_/ /" << endl;
	cout << "/ /___/ ___ |/ _, _/    / _, _/ /___/ /|  / / / / ___ |/ /___    ___/ /  / /___/ // / / /___/ /  / /" << endl;
	cout << "\\____/_/  |_/_/ |_|    /_/ |_|\\_____/_/ |_/ /_/ /_/  |_/_____/   /____/  /_//____//_/ /_____/_/  /_/" << endl;
	cout << endl << endl;
	if (y == 1)
	{
		cout << "Enter the following keys for the specific currency " << endl;
		cout << " - 1 for USD" << endl;
		cout << " - 2 for Dinar" << endl;
		cout << " - 3 for Euro" << endl;
		cout << " - 4 for Pound" << endl;
		cout << " - 5 for Rayal" << endl;
		cout << endl;
		cin >> cr;
		cin.ignore();

		if (cr == 1)
		{
			x = t / 286.6;
			cout << " Yor amount is " << x << " USD" << endl;
		}
		else if (cr == 2)
		{
			x = t / 928.5;
			cout << " Yours amaount is " << x << " Dinar" << endl;
		}
		else if (cr == 3)
		{
			x = t / 307.4;
			cout << " Yours amaount is " << x << " Euro" << endl;
		}
		else if (cr == 4)
		{
			x = t / 356.9;
			cout << " Yours amaount is " << x << " Pound" << endl;
		}
		else if (cr == 5)
		{
			x = t / 76.4;
			cout << " Yours amaount is " << x << " Rayal" << endl;
		}
		else
		{
			cout << "ERROR !  *_*" << endl;

		}
	}

	else if (y == 2)
	{
		cout << "Your total bill for " << f << " days will be " << t << " Rs" << endl;
	}
	else
	{
		cout << "INVALID OPTION !  *_*" << endl;
	}
}

int main()
{
	cout << "   _________    ____       ____  _______   ___________    __       _______  _____________________  ___" << endl;
	cout << "  / ____/   |  / __ \\     / __ \\/ ____/ | / /_  __/   |  / /      / ___/\\ \\/ / ___/_  __/ ____/  |/  /" << endl;
	cout << " / /   / /| | / /_/ /    / /_/ / __/ /  |/ / / / / /| | / /       \\__ \\  \\  /\\__ \\ / / / __/ / /|_/ /" << endl;
	cout << "/ /___/ ___ |/ _, _/    / _, _/ /___/ /|  / / / / ___ |/ /___    ___/ /  / /___/ // / / /___/ /  / /" << endl;
	cout << "\\____/_/  |_/_/ |_|    /_/ |_|\\_____/_/ |_/ /_/ /_/  |_/_____/   /____/  /_//____//_/ /_____/_/  /_/" << endl;
	cout << endl << endl;
	cout << "--------------------------------------* WELCOME TO OUR CAR RENTAL SYSTEM *----------------------------------------" << endl;
	cout << endl;
	selection();
	string u;
	cout << endl;
	cout << "Enter next " << endl;
	getline(cin, u);
	cin.ignore();
	system("cls");

	cout << "   _________    ____       ____  _______   ___________    __       _______  _____________________  ___" << endl;
	cout << "  / ____/   |  / __ \\     / __ \\/ ____/ | / /_  __/   |  / /      / ___/\\ \\/ / ___/_  __/ ____/  |/  /" << endl;
	cout << " / /   / /| | / /_/ /    / /_/ / __/ /  |/ / / / / /| | / /       \\__ \\  \\  /\\__ \\ / / / __/ / /|_/ /" << endl;
	cout << "/ /___/ ___ |/ _, _/    / _, _/ /___/ /|  / / / / ___ |/ /___    ___/ /  / /___/ // / / /___/ /  / /" << endl;
	cout << "\\____/_/  |_/_/ |_|    /_/ |_|\\_____/_/ |_/ /_/ /_/  |_/_____/   /____/  /_//____//_/ /_____/_/  /_/" << endl;
	cout << endl << endl;
	cout << endl;
	information();
	cout << endl<<endl;

	booking();
	cout << endl;
	cout << "Enter next " << endl;
	getline(cin, u);
	cin.ignore();
	system("cls");

	cout << "   _________    ____       ____  _______   ___________    __       _______  _____________________  ___" << endl;
	cout << "  / ____/   |  / __ \\     / __ \\/ ____/ | / /_  __/   |  / /      / ___/\\ \\/ / ___/_  __/ ____/  |/  /" << endl;
	cout << " / /   / /| | / /_/ /    / /_/ / __/ /  |/ / / / / /| | / /       \\__ \\  \\  /\\__ \\ / / / __/ / /|_/ /" << endl;
	cout << "/ /___/ ___ |/ _, _/    / _, _/ /___/ /|  / / / / ___ |/ /___    ___/ /  / /___/ // / / /___/ /  / /" << endl;
	cout << "\\____/_/  |_/_/ |_|    /_/ |_|\\_____/_/ |_/ /_/ /_/  |_/_____/   /____/  /_//____//_/ /_____/_/  /_/" << endl;
	cout << endl << endl;
	if (d == "2")
	{
		cout << "At which date do you want car  : ";
		getline(cin, e);

		cout << "\n\t\t                       Car Rental - Customer Invoice                  " << endl;
		cout << "\t\t	///////////////////////////////////////////////////////////" << endl;
		cout << "\t\t	| Invoice No. :" << "------------------|" << setw(15) << "#Cnb81353" <<setw(10)<< " |" << endl;
		cout << "\t\t	| Customer Name:" << "-----------------|" << setw(15) << n <<setw(10)<< " |" << endl;
		cout << "\t\t	| Booking Date :" << "---------------|" << setw(15) << e <<setw(10)<< "|" << endl;
		cout << "\t\t	| Phone Number :" << "---------------------|" << setw(15) <<setw(10)<< "pn" << "     |" << endl;
		cout << "\t\t	 ________________________________________________________" << endl;
		cout << "\n";
		cout << " " << endl;
		cout << "\t\t	///////////////////////////////////////////////////////////" << endl;
		cout << "\t\t  Your Payment and Car will be booked on  :" << setw(15) << e  << endl;
		cout << "\t\t	///////////////////////////////////////////////////////////" << endl;
	}
	else if (d == "1")
	{

		cout << endl;

		rate();
		system("CLS");
		choice();
		int g;
		cout << "Enter next for you 'payment receipt' " << endl;
		cin >> g;
		system("cls");
		cout << "--------------------------------------* WELCOME TO OUR CAR RENTAL SYSTEM *----------------------------------------" << endl;
		cout << endl;
		cout << "\n\t\t                       Car Rental - Customer Invoice                  " << endl;
		cout << "\t\t	///////////////////////////////////////////////////////////" << endl;
		cout << "\t\t	| Invoice No. :" << "------------------|" << setw(10) << "#Cnb81353" << " |" << endl;
		cout << "\t\t	| Customer Name:" << "-----------------|" << setw(10) << n << " |" << endl;
		cout << "\t\t	| Number of days :" << "---------------|" << setw(10) << f << " |" << endl;
		cout << "\t\t	| Licence Number :" << "--------|" << setw(10) << ln << " |" << endl;
		cout << "\t\t	| Phone Number :" << "---------------------|" << setw(10) << "pn" << " |" << endl;
		cout << "\t\t	 ________________________________________________________" << endl;
		cout << "\n";
		cout << "\t\t	| Total Rental Amount is :" << "-------|" << setw(10) << t << " |" << endl;
		cout << "\t\t	 ________________________________________________________" << endl;
		cout << " " << endl;
		cout << "\t\t	///////////////////////////////////////////////////////////" << endl;

		if (c == 1)
		{
			if (a == 1)
			{
				if (k == 1)
				{
					cout << " \t\t\tCar selected : Tesla Model S" << endl;
					
				}
				else if (k == 2)
				{
					cout << " \t\t\tCar selected : Tesla Model X" << endl;
					
				}
				else
				{
					cout << "*_*" << endl;
				}

			}
			else if (a == 2)
			{
				if (k == 1)
				{
					cout << " \t\t\tCar selected : Tesla Model 3" << endl;
					
				}
				else if (k == 2)
				{
					cout << "\t\t\t Car selected : Tesla Model Y" << endl;
					
				}
				else
				{
					cout << "*_*" << endl;
				}
			}
			else
			{
				cout << "*_*" << endl;
			}
		}
		else if (c == 2)
		{
			if (a == 1)
			{
				if (k == 1)
				{
					cout << " \t\t\tCar selected : BMW 7 series" << endl;
					
				}
				else if (k == 2)
				{
					cout << "\t\t\t Car selected : BMW X 7" << endl;
					
				}
				else
				{
					cout << "*_*" << endl;
				}
			}
			else if (a == 2)
			{
				if (k == 1)
				{
					cout << "\t\t \tCar selected : BMW 3 series " << endl;
					
				}
				else if (k == 2)
				{
					cout << " \t\t\tCar selected : BMW X 1" << endl;
					
				}
				else
				{
					cout << "*_*" << endl;
				}
			}
			else
			{
				cout << "*_*" << endl;
			}
		}
		else if (c == 3)
		{
			if (a == 1)
			{
				if (k == 1)
				{
					cout << " \t\t\tCar selected : Audi A 8" << endl;
				}
				else if (k == 2)
				{
					cout << "\t\t\t Car selected : Audi Q 8" << endl;
				}
				else
				{
					cout << "*_*" << endl;
				}
			}
			else if (a == 2)
			{
				if (k == 1)
				{
					cout << " \t\t\tCar selected : Audi A 3" << endl;
					
				}
				else if (k == 2)
				{
					cout << "\t\t\t Car selected : Audi Q 3" << endl;
					
				}
				else
				{
					cout << "*_*" << endl;
				}
			}
			else
			{
				cout << "*_*" << endl;
			}
		}
		else if (c == 4)
		{
			if (a == 1)
			{
				if (k == 1)
				{
					cout << "\t\t \tCar selected : Ferrari 488 GTB" << endl;
					
				}
				else if (k == 2)
				{
					cout << " \t\t\tCar selectd : Ferrari Portofino" << endl;
					
				}
				else
				{
					cout << "*_*" << endl;
				}
			}
			else if (a == 2)
			{
				if (k == 1)
				{
					cout << "\t\t \tCar selected : Ferrari F 8" << endl;
					
				}
				else if (k == 2)
				{
					cout << " \t\t\tCar selected : Ferrari Roma" << endl;
					
				}
			}
			else
			{
				cout << "*_*" << endl;
			}
		}
		else if (c == 5)
		{
			if (a == 1)
			{
				if (k == 1)
				{
					cout << "\t\t\t Car selected : Mercedes-Benz S-class" << endl;
					
				}
				else if (k == 2)
				{
					cout << " \t\t\tCar selected : Mercedes-Benz GLE" << endl;
					
				}
				else
				{
					cout << "*_*" << endl;
				}
			}
			else if (a == 2)
			{
				if (k == 1)
				{
					cout << " \t\t\tCar selected : Mercedes-Benz A-class" << endl;
					
				}
				else if (k == 2)
				{
					cout << " \t\t\tCar selected : Mercedes-Benz GLA " << endl;
		
				}
				else
				{
					cout << "*_ *" << endl;
				}
			}
			else
			{
				cout << "*_*" << endl;
			}
		}
		else
		{
			cout << " ERROR ! *_*" << endl;
		}
		cout << "\t\t	///////////////////////////////////////////////////////////" << endl;
	}

	
	cout << " ________  __                            __              __      __                         __  __ \n";
	cout << "/        |/  |                          /  |            /  \\    /  |                       /  |/  |\n";
	cout << "$$$$$$$$/ $$ |____    ______   _______  $$ |   __       $$  \\  /$$/______   __    __       $$ |$$ |\n";
	cout << "   $$ |   $$      \\  /      \\ /       \\ $$ |  /  |       $$  \\/$$//      \\ /  |  /  |      $$ |$$ |\n";
	cout << "   $$ |   $$$$$$$  | $$$$$$  |$$$$$$$  |$$ |_/$$/         $$  $$//$$$$$$  |$$ |  $$ |      $$ |$$ |\n";
	cout << "   $$ |   $$ |  $$ | /    $$ |$$ |  $$ |$$   $$<           $$$$/ $$ |  $$ |$$ |  $$ |      $$/ $$\n";
	cout << "   $$ |   $$ |  $$ |/$$$$$$$ |$$ |  $$ |$$$$$$  \\           $$ | $$ \\__$$ |$$ \\__$$ |       __  __\n";
	cout << "   $$ |   $$ |  $$ |$$    $$ |$$ |  $$ |$$ | $$  |          $$ | $$    $$/ $$    $$/       /  |/  |\n";
	cout << "   $$/    $$/   $$/  $$$$$$$/ $$/   $$/ $$/   $$/           $$/   $$$$$$/   $$$$$$/        $$/ $$\n";
	cout << endl;
}

```
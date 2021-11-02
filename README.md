#include <iostream>
#include <string>
using namespace std;
double average() {
	
    double price1, price2, averageprice;
	cout << "\nEnter Product1 Price: ";
	cin >> price1;
	if (cin.fail() || price1 < 0 || price1 > 100) {
		cout << "Product price 1 is not a valid input";
		return -69;
	}
	cout << "\nEnter Product2 Price: ";
    cin >> price2;
	if (cin.fail() || price2 < 0 || price2 > 100) {
		cout << "Product price 2 is not a valid input";
		return -69;
	}
	averageprice = (price1 + price2) / 2;	

	return averageprice;		
}
void DisplayMessage(double averageprice) {
		
	if (averageprice >= 70 && averageprice <= 100) cout << "\nYou're spending quite a lot without saving anything.\n";	
	if (averageprice >= 50 && averageprice <= 69) cout << "\nMedium spending and saving, well done.\n";			
	if (averageprice >= 10 && averageprice <= 49) cout << "\nIt seems like you didn't spend much.\n";	
	if (averageprice >= 0 && averageprice <= 9) cout << "\nYou practically didn't buy anything at all\n";

}
int main() {

	string fullname;  double averageprice;	int age; char userInput; string buffer;
	cout << "Would you like to calculate the average prices of your products (0-100) ? Input (Y/N)\n";
	cin >> userInput;
	switch (userInput)
	{
	case 'y':
	case 'Y':
		cout << "Enter Fullname: ";
		cin >> buffer; // I included this because when you Input Y or N a \n is created after pressing enter and getline gets skipped see screenshot below.
		getline(cin, fullname);
		cout << "\nEnter Age: ";
		cin >> age;
		if (cin.fail() || age < 0) {
			cout << "Invalid Input";
			return -69;
		}
		averageprice = average();
		if (averageprice >= 0)
		{   
			cout << '\n' << buffer << fullname << " age : " << age << " Spent an average of : " << averageprice << endl;
            DisplayMessage(averageprice);
		}		
		break;
	case 'n':
	case 'N':
		cout << "Okey GoodBye, Thank you" << endl;
		break;
	    default:
			cout << "Invalid Input" << endl;
		break;
	}
}

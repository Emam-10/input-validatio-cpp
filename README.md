# input-validatio-cpp
//code example in c++demonstrating input validation using cin.fail ( ) ,cin.clear( ),cin.ignore ( ) to ensure user inputs are valid numbers


#include <iostream>
using namespace std;

int readnumber()
{
	//Function of read valid number from the user
	int number;
	cout << "Please enter number \n";
	cin >> number;


	//check if input is invalid 
	while (cin.fail())
	{
		cin.clear();   //reset the input state to clear the  error flag 
		cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');  //ignor all invalid  characters in the input buffer up to the newline
		cout << "Invalid number, enter the vald one" << endl;
		cin >> number;
	}
	return number;
}



int main()
{
	cout << "The number is :" << readnumber() << endl;

	return 0;
}


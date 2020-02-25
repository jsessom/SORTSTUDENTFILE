# SORTSTUDENTFILE
EXTRACTS STUDENTS ID NAME GPA FROM FILE PUTS IN ARRAY THEN SORTS THEN DISPLAYS IN ORDER
#include <iostream>
#include <fstream>
#include <string>
using namespace std;


struct record // Linked list
{
	int id;
	float gpa;
	string name;
};



int main()
{
	
	int index[10];
	record student[10];
	student[10].gpa;
	student[10].id;
	student[10].name;
	int i, j;
	


	ifstream inputfile;
	inputfile.open("Z:\\CS-246\\ConsoleApplication5\\Studentdatafile.txt");

	if (!inputfile)
	{
		cerr << "File is not open." << endl;
		exit(1);
	}

	
	/*while (!inputfile.eof())
	{
		i = 0;
	inputfile >> student[i].name;
	inputfile>> student[i].id;
	inputfile >> student[i].gpa;
	cout << " Name =" << student[i].name << endl;
	cout << " ID number =" << student[i].id << endl;
	cout << "GPA  =" << student[i].gpa << endl;
	cout << endl;

	}
	*/
	for (int i = 0; i < 10; i++)
	{
			
	inputfile >> student[i].name;
	inputfile>> student[i].id;
	inputfile >> student[i].gpa;
	cout << " Name =" << student[i].name << endl;
	cout << " ID  =" << student[i].id << endl;
	cout << " GPA  =" << student[i].gpa << endl;
	cout << endl;
	
	}
	
	

	
	for (int i = 0; i < 10; i++)
	{

		index[i] = i;

	}
	
	j = 0;

	for (int i = 0; i < 9; i++)
	{

		for (int j=i+1; j < 10; j++)
		{
			 // initialization
			int temp;
			if (student[index[i]].id > student[index[j]].id)
			{
				
				temp = index[i];
				index[i] = index[j];
				index[j] = temp;


			}


		}

	}

	for (int i = 0; i < 10; i++)
	{

		cout << "Student ID: " << student[index[i]].id << endl
			<< "Student Name:" << student[index[i]].name << endl
		<< "Student GPA: " << student[index[i]].gpa << endl;
		cout << endl;
	}
	
	return 0;
}

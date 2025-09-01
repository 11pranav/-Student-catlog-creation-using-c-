Add class comment…

#include <iostream>
#include <string>

using namespace std;
class Student
{
 private:
 int rollno;
 string name,gender;
 static int rollno_generator;
 public:
 	static int generate_rollno()
 	{
 		return(++rollno_generator);
	 }
 void register_student(string name,string gender)	
 {
 	this->name=name;
 	this->gender=gender;
 	this->rollno=generate_rollno();
 	cout<<"\nhi "<<name<<" remeber your roll no is:"<<rollno;
 }
 void display()
 {
 	cout<<endl<<"Roll no:"<<rollno<<"\tName:"<<name<<"\tGender:"<<gender;
 }
 int get_rollno()
 {
 	return rollno;
 }
};
int Student::rollno_generator=2500;

int main() 
{
	string name,gender;
	Student s[3];//This is an area of object. 
	for(int i=0;i<3;i++)
	{
		cout<<"\nEnter name and gender\n";
		cin>>name>>gender;
		s[i].register_student(name,gender);
	}
	for(int i=0;i<3;i++)
	{
		s[i].display();
	}	
	//search on rollno:
	cout<<"Enter rollno:";
	int rollno_to_search;
	cin>>rollno_to_search;
	for(int i=0;i<3;i++)
	{
		if(rollno_to_search==s[i].get_rollno())//Will access private data and pass it out. 
			s[i].display();
    }
    
}

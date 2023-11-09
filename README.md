# OOPS_Ass-2
Acs 231043 assignment # 2 question 1 part b
#include <iostream> 

using namespace std; 

  

class Course { 

public: 

	Course(const string& courseName, int capacity); 

	~Course(); 

	string getCourseName() const; 

	void addStudent(const string& name); 

	string* getStudents() const; 

	int getNumberOfStudents() const; 

	void displayStudents(); 

  

private: 

	string courseName; 

	string* students; 

	int numberOfStudents; 

	int capacity; 

}; 

  

Course::Course(const string& courseName, int capacity) 

{ 

	numberOfStudents = 0; 

	this->courseName = courseName; 

	this->capacity = capacity; 

	students = new string[capacity]; 

} 

  

Course::~Course() 

{ 

	delete[]students; 

} 

  

string Course::getCourseName() const 

{ 

	return courseName; 

} 

  

void Course::addStudent(const string& name) 

{ 

	students[numberOfStudents] = name; 

	numberOfStudents++; 

} 

  

string* Course::getStudents() const 

{ 

	return students; 

} 

  

int Course::getNumberOfStudents() const 

{ 

	return numberOfStudents; 

} 

  

void Course::displayStudents() { 

	for (int i = 0; i < capacity; i++) { 

		cout << students[i] << endl; 

	} 

} 

  

int main() { 

	Course course1("Course1", 4); 

	course1.addStudent("taha"); 

	course1.addStudent("Ali"); 

	course1.addStudent("Hassan"); 

	course1.addStudent("Obaid"); 

  

Course course2=course1; 

  

	cout << "course 1 students" << endl; 

	course1.displayStudents(); 

  

	cout << "course 2 students" << endl; 

	course2.displayStudents(); 

} 

class Student {
public:
	const static int numDaysSize = 3;

private: 

	string studentID;
	string firstName;
	string lastName;
	string email;
	int age;
	int numDays[numDaysSize];
	DegreeProgram degreeProgram; 

public:

	// Constructors
	Student();
	Student(string studentID, string firstName, string lastName, string email, int age, int numDays[], DegreeProgram degreeProgram);

	//Destructor
	~Student();

	// getters
    string getID();
	string getFirstName();
	string getLastName();
	string getEmail();
	int getAge();
    int *getNumDays(); 
	DegreeProgram getDegreeProgram(); 

	// setter
	void setID(string ID);
	void setFirstName(string firstName);
	void setLastName(string lastName);
	void setEmail(string email);
	void setAge(int age);
	void setNumDays(const int numDays[]);
	void setDegreeProgram(DegreeProgram degree);

	// Virtual functions
	 void print();

};

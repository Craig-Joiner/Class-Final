class Roster {

public:

	int lastIndex = -1;
	Student* classRosterArray[5];

	void parse(string row);
	void add(string studentID, string firstName, string lastName, string email, int age, int daysInCourse1, int daysInCourse2, int daysInCourse3, DegreeProgram degree); // may need to be degreeProgram
	void remove(string studentID);
	void printAll();
	void printAverageDaysInCourse(string studentID);
	void printInvalidEmails();
	void printByDegreeProgram(DegreeProgram degree);

	// destructor
	~Roster();
};

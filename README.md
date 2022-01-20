// Constructors
Student::Student() {

	this->studentID = "";
	this->firstName = "";
	this->lastName = "";
	this->email = "";
	this->age = 0;
	for (int i = 0; i < numDaysSize; i++) this->numDays[i] = 0;
	this->degreeProgram = DegreeProgram::SOFTWARE;
}

Student::Student(string studentID, string firstName, string lastName, string email, int age, int numDays[], DegreeProgram degreeProgram) {

	this->studentID = studentID;
	this->firstName = firstName;
	this->lastName = lastName;
	this->email = email;
	this->age = age;
	for (int i = 0; i < numDaysSize; i++) this->numDays[i] = numDays[i];
	this->degreeProgram = degreeProgram;
}

//Destructor
Student::~Student() {}

//getters
string Student::getID() { return this->studentID;}
string Student::getFirstName() {return this->firstName;}
string Student::getLastName() {return this->lastName;}
string Student::getEmail() {return this->email;}
int Student::getAge() {return this->age;}
int* Student::getNumDays() {return this->numDays;}
DegreeProgram Student::getDegreeProgram() {return this->degreeProgram;}

//setters
void Student::setID(string ID) { this->studentID = ID; } 
void Student::setFirstName(string firstname) { this->firstName = firstname; }
void Student::setLastName(string lastname) { this->lastName = lastname; }
void Student::setEmail(string email) { this->email = email; }
void Student::setAge(int age) { this->age = age; }
void Student::setNumDays(const int numDays[]) 
{
	for (int i = 0; i < numDaysSize; i++) this->numDays[i] = numDays[i];
}
void Student::setDegreeProgram(DegreeProgram degreeProgram) { this->degreeProgram = degreeProgram; } 

void Student::print() {
	cout << this->studentID << '\t';
	cout << this->firstName << '\t';
	cout << this->lastName << '\t';
	cout << this->email << '\t';
	cout << this->age << '\t';
	cout << this->numDays[0] << ',';
	cout << this->numDays[1] << ',';
	cout << this->numDays[2] << '\t';
	cout << degreeProgramStrings[(int)this->degreeProgram] << '\n';
	cout << endl;
}

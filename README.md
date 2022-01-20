# Class-Final
I learned how to use all the funditmentals of c++, like vectors, arrays, classes. Also how to implement public and private class structures.

void Roster::parse(string row) {

	regex regex("\\,");
	std::vector<string>splitter(std::sregex_token_iterator(row.begin(), row.end(), regex, -1), std::sregex_token_iterator());

	DegreeProgram degree = DegreeProgram::SOFTWARE;
	if(splitter.at(8).back() == 'K') degree = DegreeProgram::NETWORK;
	if (splitter.at(8).back() == 'Y') degree = DegreeProgram::SECURITY;
	add(splitter.at(0), splitter.at(1), splitter.at(2), splitter.at(3), stod(splitter.at(4)), stod(splitter.at(5)), stod(splitter.at(6)), stod(splitter.at(7)), degree);
}

void Roster::add(string studentID, string firstName, string lastName, string email, int Age, int daysC1, int daysC2, int daysC3, DegreeProgram degreeProgram) {
	int parr[3] = { daysC1, daysC2, daysC3 };
	classRosterArray[++lastIndex] = new Student(studentID, firstName, lastName, email, Age, parr, degreeProgram); // need to change classrosterarray
}

void Roster::printAll() {

	for (int i = 0; i <= Roster::lastIndex; i++) Roster::classRosterArray[i]->print();
}

void Roster::printByDegreeProgram(DegreeProgram degree) {

	for (int i = 0; i <= Roster::lastIndex; i++) 
		if (Roster::classRosterArray[i]->getDegreeProgram() == degree) classRosterArray[i]->print();
	
}

void Roster::printInvalidEmails() {
	for (int i = 0; i <= Roster::lastIndex; i++) {

		string id = classRosterArray[i]->getEmail();
		if ((id.find(' ') != string::npos) || (id.find('.') == string::npos) || (id.find('@') == string::npos))

			cout << id << " is invalid!" << endl;
		}
	}

void Roster::printAverageDaysInCourse(string studentID) {
		for (int i = 0; i <= Roster::lastIndex; i++) {
			if (classRosterArray[i]->getID() == studentID) {

				cout << studentID << ": ";
				cout << (classRosterArray[i]->getNumDays()[0]
					+ classRosterArray[i]->getNumDays()[1]
					+ classRosterArray[i]->getNumDays()[2]) / 3.0 << endl;
			}
		}
	}

void Roster::remove(string studentID) {
	bool success = false;
	for (int i = 0; i <= Roster::lastIndex; i++)
	{
		if (classRosterArray[i]->getID() == studentID)
		{
			success = true;
			delete classRosterArray[i];
			classRosterArray[i] = classRosterArray[i + 1];
			classRosterArray[i + 1] = classRosterArray[i + 2];
			Roster::lastIndex--;
		}
	}

   if (success) {

	cout << "Removing " << studentID << endl;
	printAll();
}
   else 
	   cout << "The Student with the ID: " << studentID << " was not found." << endl;
}

Roster::~Roster() {

	for (int i = 0; i < lastIndex; i++) {
		delete classRosterArray[i];
		classRosterArray[i] = nullptr;
	}
}

# Class-Final
I learned how to use all the funditmentals of c++, like vectors, arrays, classes. Also how to implement public and private class structures.

int main() {
    Roster classRoster;
    const int numDays = 5;

    // Student information
    const string studentData[] = {
     "A1,John,Smith,John1989@gm ail.com,20,30,35,40,SECURITY",
     "A2,Suzan,Erickson,Erickson_1990@gmailcom,19,50,30,40,NETWORK",
     "A3,Jack,Napoli,The_lawyer99yahoo.com,19,20,40,33,SOFTWARE",
     "A4,Erin,Black,Erin.black@comcast.net,22,50,58,40,SECURITY",
     "A5,William,Joiner,wjoine6@wgu.edu,24,12,25,54,SOFTWARE"
    };

    cout << "Course: Scripting and Programming Applications (C867)" << endl;
    cout << "Programming Language Used: C++" << endl;
    cout << "Student ID: 006708286" << endl;
    cout << "Name: William Joiner" << endl << endl;

    for (int i = 0; i < numDays; i++)
        classRoster.parse(studentData[i]);

    cout << "Displaying all Students: " << endl;
    for (int i = 0; i < 5; i++) {
        cout << studentData[i] << endl;
    }

    cout << endl << "Displaying Students with invalid emails: " << endl;
    classRoster.printInvalidEmails();

    cout << endl << "Displaying average time to complete the class: " << endl;
      for (int i = 0; i < numDays; i++)
        classRoster.printAverageDaysInCourse(classRoster.classRosterArray[i]->getID());

    cout << endl << "Displaying all Students in the software degree program: " << endl;
    classRoster.printByDegreeProgram(DegreeProgram::SOFTWARE);
      

    // removing student A3
    classRoster.remove("A3");

    // removing student A3 again
    classRoster.remove("A3");
    system("pause");

    return 0;
}

#include <iostream>
#include <ctime>
#include <cstring>
#include <cmath>
using namespace std;

void day_occur_time(int year) {

	// stores days in a week 
	string days[] = {"Monday", "Tuesday", "Wednesday", 
		"Thursday", "Friday", "Saturday", "Sunday" };
	
	// Initialize all counts as 52
	int L[7];
	for (int i = 0; i < 7; i++) {
		L[i] = 52;
	}
	
	// Find the index of the first day
	// of the year
	int pos = -1;
	time_t t = time(NULL);
	tm* timePtr = localtime(&t);
	timePtr->tm_year = year - 1900;
	timePtr->tm_mon = 0;
	timePtr->tm_mday = 1;
	mktime(timePtr);
	char buffer[80];
	strftime(buffer, 80, "%A", timePtr);
	string day(buffer);
	for (int i = 0; i < 7; i++) {
		if (day == days[i]) {
			pos = i;
		}
	}
	
	// mark the occurrence to be 53 of 1st day
	// and 2nd day if the year is leap year
	if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0) {
		L[pos] += 1;
		L[(pos+1)%7] += 1;
	} else {
		L[pos] += 1;
	}
	
	// Print the days
	for (int i = 0; i < 7; i++) {
		cout << days[i] << " " << L[i] << endl;
	}
}

int main() {
	int year = 2019;
	day_occur_time(year);
	return 0;
}

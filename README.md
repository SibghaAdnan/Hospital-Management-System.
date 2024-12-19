# Hospital-Management-System.

#include <iostream>
#include <string>
using namespace std;

//Define a Structure to hold patient detail
struct Patient 
{
    int id;      
    string name;   
    int age;     
    string disease;  
    string contact;
};

// Function to add a new patient
void addPatient(Patient patients[], int &count, int maxPatients) 
{
	//cheak if the array has reached its maximum capacity
    if (count >= maxPatients) 
	{
        cout << "No space to add more patients."<<endl;
        return;
    }
    
    //Prompt user to enter patient detail
    cout << "\nEnter Patient Details:"<<endl;
    
    cout << "ID: ";
    cin >> patients[count].id;
    //clear input buffers
    cin.ignore();
    
    cout << "Name: ";
    getline(cin,patients[count].name);
    
    cout << "Age: ";
    cin >> patients[count].age;
    cin.ignore();    
	 
    cout << "Disease: ";
    getline(cin,patients[count].disease);
   
    cout << "Contact: ";
    cin>> patients[count].contact;
    //Increment the patient count
    count++;
    
    //clear the console and display a success message
    system("cls");
    
        system("color C4");
    for (int i = 0; i < 12; i++) 
    {
        cout << endl;
    }
    cout << "                          *******************Patient added successfully*******************" << endl;

    //wait for the user to press enter 
    cin.get();
    cin.ignore();
    system("cls");
}
// Function to display all patient
void displayPatients(Patient patients[], int count) 
{
	//cheak if there are any patient to display
    if (count == 0) 
	{
        cout << "No patients in the list."<<endl;
        return;
    }
    
    cout << "\n--- Patient Details ---\n";
    
    //using for loop for display patient detail.
    for (int i = 0; i < count; i++) 
	{
        cout << "ID: " << patients[i].id << "\n";
        cout << "Name: " << patients[i].name << "\n";
        cout << "Age: " << patients[i].age << "\n";
        cout << "Disease: " << patients[i].disease << "\n";
        cout << "Contact: " << patients[i].contact << "\n";
        cout << "----------------------\n";
    }
    
    cin.get();
    cin.ignore();
    system("cls");
    
        system("color C2");
    for (int i = 0; i < 12; i++) 
    {
        cout << endl;
    }
    cout << "                          *******************Display Patient Successfully*******************" << endl;

    cin.get();
    cin.ignore();
    system("cls");
}

// Function to update patient details
void updatePatient(Patient patients[], int count) 
{
	 // Check if there are any patients to update
    if (count == 0) 
	{
        cout << "No patients to update."<<endl;
        return;
    }

    int id;
    cout << "\nEnter Patient ID to update: ";
    // Read the ID of the patient to update
    cin >> id;

    // Search for the patient with the given ID
    for (int i = 0; i < count; i++) 
	{
		//update patient detail inside if statement.
        if (patients[i].id == id) 
		{
			 // Prompt user to update the details of the found patient
            cout << "\nUpdating details for Patient ID " << id << endl;
            cin.ignore();
            
            cin.ignore();
            cout << "New Name: ";
            getline(cin,patients[i].name);
            
            cout << "New Age: ";
            cin >> patients[i].age;
            
            cin.ignore();
            cout << "New Disease: ";
            getline(cin,patients[i].disease);
            
            cout << "New Contact: ";
            cin>>patients[i].contact;
            // Clear the console and display a success message
            system("cls");
            
                system("color C4");
            for (int i = 0; i < 12; i++) 
            {
                cout << endl;
            }
            cout << "                          *******************Updated Patient Successfully*******************" << endl;

            cin.get();
            cin.ignore();
            system("cls");
            
            return;
        }
        
    }
    
    // If the patient with the given ID is not found
    cout << "Patient with ID " << id << " not found."<<endl;
    system("cls");
    
               system("color C4");
            for (int i = 0; i < 12; i++) 
            {
                cout << endl;
            }
            cout << "                          *******************Invalid Patient Id*******************" << endl;

            cin.get();
            cin.ignore();
            system("cls");
}

// Function to remove a patient
void removePatient(Patient patients[], int &count) 
{
	 // Check if there are any patients to remove
    if (count == 0) 
	{
        cout << "No patients to remove.\n";
        return;
    }

    int id;
    cout << "\nEnter Patient ID to remove: ";
    // Read the ID of the patient to remove
    cin >> id;
    
    // Search for the patient with the given ID
    for (int i = 0; i < count; i++) 
	{
        if (patients[i].id == id) 
		{
			// Shift the patients array to fill the gap
            for (int j = i; j < count - 1; j++) 
			{
				patients[j] = patients[j + 1]; 
            }
            //Decrement the patient count
            count--;
            system("cls");
            
                system("color C4");
            for (int i = 0; i < 12; i++) 
            {
                cout << endl;
            }
            cout << "                          *******************Remove Patient Successfully*******************" << endl;

            cin.get();
    
            cin.ignore(); 
            system("cls");
            return;
        }
    }

    cout << "Patient with ID " << id << " not found.\n";
    system("cls");
    
    system("color C4");
            for (int i = 0; i < 12; i++) 
            {
                cout << endl;
            }
        cout << "                          *******************Invalid Patient Id*******************" << endl;

            cin.get();
            cin.ignore();
            system("cls");
}

// Main function to display the menu and manage the system
int main() 
{
	// Maximum number of patients allowed in the system
    int maxPatients=100;
    // Array to store patient details
    Patient patients[100]; 
    // Current count of patients
    int patientCount = 0; 
    
    //Display a welcome message
    system("color B5");
              
	for (int i = 0; i < 12; i++) 
	{
        cout << endl;  
    }
   
    cout <<"                          *******************************************************"<<endl;
    cout <<"                          *                                                     *"<<endl;
    cout <<"                          *         WELCOME TO HOSPITAL MANAGEMENT SYSTEM       *"<<endl;
    cout <<"                          *                                                     *"<<endl;
    cout <<"                          *******************************************************"<<endl;
    
    cin.get();
    system("cls");
       
    int choice;
    do 
	{
    		system("color D7");
        cout << "\n--- Hospital Management System ---\n";
        cout << "1. Add New Patient"<<endl;
        cout << "2. Display Patients"<<endl;
        cout << "3. Update Patient Details"<<endl;
        cout << "4. Remove Patient"<<endl;
        cout << "5. Exit"<<endl;
        
        cout << "Enter your choice: ";
        cin >> choice;
        system("cls");

        // Handle menu choices
        switch (choice) 
		{
            case 1:
            		system("color A7");
            		
                addPatient(patients, patientCount, maxPatients);
                break;
            case 2:
            		system("color D7");
            		
                displayPatients(patients, patientCount);
                break;
            case 3:
            		system("color A7");
            		
                updatePatient(patients, patientCount);
                break;
            case 4:
            		system("color D7");
            		
                removePatient(patients, patientCount);
                break;
            case 5:
            	
                cout << "Exiting the system.\n*********************** Thank you! **********************\n";
                break;
            default:
            	
                cout << "Invalid choice. Please try again."<<endl;
        }
        
    } 
    // Repeat until the user chooses to exit
	while (choice != 5);

    return 0;
    
}

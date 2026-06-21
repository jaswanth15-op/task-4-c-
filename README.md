#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<string> tasks;
    int choice;

    do {
        cout << "\n===== TO-DO LIST =====\n";
        cout << "1. Add Task\n";
        cout << "2. View Tasks\n";
        cout << "3. Delete Task\n";
        cout << "4. Exit\n";
        cout << "Enter Choice: ";
        cin >> choice;

        cin.ignore();

        switch(choice) {
            case 1: {
                string task;
                cout << "Enter Task: ";
                getline(cin, task);
                tasks.push_back(task);
                cout << "Task Added!\n";
                break;
            }

            case 2: {
                cout << "\nTasks:\n";
                for(int i = 0; i < tasks.size(); i++) {
                    cout << i + 1 << ". " << tasks[i] << endl;
                }
                break;
            }

            case 3: {
                int num;
                cout << "Enter Task Number to Delete: ";
                cin >> num;

                if(num >= 1 && num <= tasks.size()) {
                    tasks.erase(tasks.begin() + num - 1);
                    cout << "Task Deleted!\n";
                } else {
                    cout << "Invalid Task Number!\n";
                }
                break;
            }

            case 4:
                cout << "Exiting...\n";
                break;

            default:
                cout << "Invalid Choice!\n";
        }

    } while(choice != 4);

    return 0;
}

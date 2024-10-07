#include <iostream>
#include <string>
#include <sstream>
#include <bitset>
#include <cmath>

using namespace std;

// Function to convert decimal to binary
string decimalToBinary(int decimal) {
    return bitset<32>(decimal).to_string(); // 32-bit representation
}

// Function to convert decimal to octal
string decimalToOctal(int decimal) {
    stringstream ss;
    ss << oct << decimal;
    return ss.str();
}

// Function to convert decimal to hexadecimal
string decimalToHexadecimal(int decimal) {
    stringstream ss;
    ss << hex << decimal;
    return ss.str();
}

// Function to convert binary to decimal
int binaryToDecimal(string binary) {
    return stoi(binary, 0, 2);
}

// Function to convert octal to decimal
int octalToDecimal(string octal) {
    return stoi(octal, 0, 8);
}

// Function to convert hexadecimal to decimal
int hexadecimalToDecimal(string hex) {
    return stoi(hex, 0, 16);
}

void menu() {
    cout << "Conversion Menu:\n";
    cout << "1. Decimal to Binary\n";
    cout << "2. Decimal to Octal\n";
    cout << "3. Decimal to Hexadecimal\n";
    cout << "4. Binary to Decimal\n";
    cout << "5. Octal to Decimal\n";
    cout << "6. Hexadecimal to Decimal\n";
    cout << "7. Exit\n";
}

int main() {
    int choice;
    bool exitProgram = false;

    while (!exitProgram) {
        menu();
        cout << "Choose a conversion option: ";
        cin >> choice;

        switch (choice) {
            case 1: {
                int decimal;
                cout << "Enter decimal number: ";
                cin >> decimal;
                cout << "Binary: " << decimalToBinary(decimal) << endl;
                break;
            }
            case 2: {
                int decimal;
                cout << "Enter decimal number: ";
                cin >> decimal;
                cout << "Octal: " << decimalToOctal(decimal) << endl;
                break;
            }
            case 3: {
                int decimal;
                cout << "Enter decimal number: ";
                cin >> decimal;
                cout << "Hexadecimal: " << decimalToHexadecimal(decimal) << endl;
                break;
            }
            case 4: {
                string binary;
                cout << "Enter binary number: ";
                cin >> binary;
                cout << "Decimal: " << binaryToDecimal(binary) << endl;
                break;
            }
            case 5: {
                string octal;
                cout << "Enter octal number: ";
                cin >> octal;
                cout << "Decimal: " << octalToDecimal(octal) << endl;
                break;
            }
            case 6: {
                string hex;
                cout << "Enter hexadecimal number: ";
                cin >> hex;
                cout << "Decimal: " << hexadecimalToDecimal(hex) << endl;
                break;
            }
            case 7: {
                exitProgram = true;
                cout << "Exiting the program..." << endl;
                break;
            }
            default: {
                cout << "Invalid option. Please choose again.\n";
            }
        }

        cout << endl;
    }

    return 0;
}

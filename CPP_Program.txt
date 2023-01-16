#include <iostream>
#include <string>

using namespace std;

int characters[128]; // Если условие, что мы используем только ASCII

int main()
{
    string input;
    getline(cin, input);
    for (char character: input) {
        if (character >= 'a' && character <= 'z') {
            characters[character - 32]++;
        } else {
            characters[character]++;
        }
    }
    
    for (char character: input) {
        if (character >= 'a' && character <= 'z') {
            character -= 32; 
        }
        
        if (characters[character] > 1) {
            cout << ')';
        } else {
            cout << '(';
        }
    }
    return 0;
}

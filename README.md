Program to reverse a string
Today in this article we will learn how to reverse a string. There are various method top reverse a sting that we will be discussing in this page.

Reversing a string is a technique so that the 1st character becomes the last character and so on.

Lets understand this with the help of an example:- 

Input sting:- RITIKA
Output sting:- AKITIR
reverse a string
Algorithm
Algorithm for C++ Program to Reverse a String

Method 1: Swapping individual characters of the string
Method 2: Using inbuilt function
Method 3: Using additional character array to store reverse
Method 4: Just printing the string in reverse from end
Method 5: updation to char.at()
C++ Program to Reverse A String
Method 1 (Program to reverse a string)
C++ Code :-
Run
#include <iostream>
#include <string.h>
using namespace std;

// function definition of the revstr()
void revstr(char *str1) {
    // declare variable
    int i, len, temp;
    len = strlen(str1);

    // use strlen() to get the length of str string
    // use or loop to iterate the string
    for(i = 0;i < len/2;i++)
    {
        //temp variable use to temporary hold the string
        temp = str1[i];
        str1[i] = str1[len - i - 1];
        str1[len - i - 1] = temp;
    }
}
int main()
{
    char str[50] = "Priyanka";
    cout << "Before reversing the string: " << str;

    revstr(str);
    
    cout<< "\nAfter reversing the string: " << str;
    return 0;
}
Output:-
Before reversing the string: priyanka 
After reversing the string: aknayirp
Method 2
We can also reverse the string using some build in functions:-

like strrev() is there in C but not in C++
We can use reverse which is defined under the header file algorithm
#include<algorithm> where str.begin() denotes the start and str.end() denotes end
Run
#include <iostream>
#include <string.h>
#include <algorithm>
using namespace std;

int main()
{
    // declare string
    string str = "PrepInsta";
    
    cout << "Before Reversal: " << str;
    
    // reverse which is defined under the header file 
    // algorithm #include
    // str.begin() denotes the start 
    // and str.end() denotes end
    
    reverse(str.begin(), str.end());
    
    cout << "\nAfter Reversal: "<< str;
    
    return 0;
}
Output:-
Before Reversal: PrepInsta
After Reversal: atsnIperP
Related Pages
Juggling algorithm for array rotation
 
Balanced Parenthesis Problem
 
Toggle each character in a string

Find the ASCII value of a character

Length of the string without using strlen() function

While loop in C
Method 3
We can also reverse the string by storing the reverse in another array and then print.

The idea is to transfer the string to another string in a reverse manner let the another array is rev.
All we need is the size of the string.
The method is to initialize a character array of the equal size and start copying the elements of the input string from the end.
And display the rev
Run
#include <iostream>
#include <string.h>
using namespace std;

int main() {
    char str[10] = "level", rev[10];
    int i, j, count = 0;
    
    cout << "String Before Reverse: " << str;
    
    // finding the length of the string
    
    while(str[count] != '\0'){
        count++;
    }
    
    j = count - 1;
    
    // Storing the array to another array
    for (i = 0; i <= count; i++) {
        rev[i] = str[j];
        j--;
    }
    
    cout << "\nString After Reverse: " << rev;
    return 0;
}
Output
String Before Reverse: level
String After Reverse: level
Method 4
This includes use of two pointers one at the starting and one at the end.
the characters are then reversed one by one
The process of reversing the string is done with the help of two pointers.
Run
#include <iostream>
#include <string.h>
using namespace std;
int main()
{
    char str[] = "priyanka";
    cout << "Original string: " << str;
    
    cout << endl << "String after reverse: ";
    
    for(int i = (strlen(str) - 1); i >= 0; i--)
        cout << str[i];
        
    return 0;
}
Output
original string: priyanka
String after reverse: aknayirp
Method 5
Write a C++ program to accept the string from the user and print the string in reverse order. in order to solve this problem use at() function

Run
/* Write a C++ program to accept the string from the user 
and print the string in reverse order. in order to 
solve this problem use at() function. */
#include <iostream>
using namespace std;
 
void revstr(string str)
{
    int i, len;
    char temp;
    len = str.length();

    for (i = 0; i < len / 2; i++) {
        
        // using str.at() function
        // str.at() returns char at index in a string
        // can throw out of range exception if requested index out of bounds
        temp = str.at(i);
        str.at(i) =str.at(len - i - 1);
        str[len - i - 1] = temp;
    }
    cout << "After reversing the string: " << str << endl;    
}
 
// Driver code
int main()
{
    string str("PrepInsta");
    
    cout << "Before reversing the string: " << str << endl;
    
    revstr(str);
    
    return 0;
}
Output
Before reversing the string: PrepInsta
After reversing the string: atsnIperP

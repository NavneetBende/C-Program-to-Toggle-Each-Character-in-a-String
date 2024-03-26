Toggle each character in a string.
In this article we will learn a C program to toggle each characters in a string i.e. to convert upper case characters to lower case characters and lower case characters to upper case characters in a string. This will help us to understand character conversion using ASCII values.

toggle each character in a string
Methods Discussed
Method 1: Using ASCII but adding/subtracting numbers to lowercase/uppercase
Method 2: Using ASCII and directly adding/subtracting characters
Method 3: Using while loop instead of a for loop
Method 4: Using recursion
Toggle Characters in a String in C
Algorithm:
Initialize the variables.
Accept the input.
Initiate a for loop.
Toggle each character.
If the element is Upper Case then we will add 32 as ASCII value of A is 65 and a is 97. 
To make Upper case to lower we need to add the difference of the both that is 97 – 65 = 32 .
To make Lower case to Upper we need to subtract 32 .
Terminate the loop.
Print toggled string.
C programming code to toggle each character in a string.
Lets have a look at the code –

Run
#include <stdio.h>
#include <string.h> 

// Make sure that have knowledge about ASCII
// if not please check - https://prepinsta.com/ascii-table/
int main()
{
    //Initializing variable.
  	char str[100];
  	int i;
  	
    //Accepting input.
  	printf("\n Please Enter any String: ");
  	gets(str);
  	
  	//Initializing for loop.
  	for (i = 0; str[i]!='\0'; i++)
  	{
  	    //Toggling characters.
  	    if(str[i] >= 'A' && str[i] <= 'Z') 
              str[i] = str[i] + 32; 
              
              
        else if(str[i] >= 'a' && str[i] <= 'z')
            str[i] = str[i] - 32;
  		
  	}

  	printf("\n Toglled string: %s", str);
  	
  	return 0;
}
Output:
Please Enter any String: PREPinsta 
Toggoled string: prepINSTA
While loop in C
Method 2
The Logic is same here we are using the ASCII value

Initialize the variables.
Accept the input.
Initiate a for loop.
Toggle each character.
Terminate the loop.
Print toggled string.
Run
#include <stdio.h>
#include <string.h>

// Make sure that have knowledge about ASCII
// if not please check - https://prepinsta.com/ascii-table/

int main() {

    char str[100];
    
    printf("Please Enter any String: ");
    gets(str);

    for (int i = 0; str[i] != '\0'; i++) {
        
        if (str[i] >= 'A' && str[i] <= 'Z')
            str[i] = str[i] + 'a' - 'A';
        
        else if (str[i] >= 'a' && str[i] <= 'z')
            str[i] = str[i] + 'A' - 'a';
    }

    printf("Toggoled string: %s", str);  // Print toggled string.
    return 0;
}
Output:
Please Enter any String: PREPinsta 
Toggoled string: prepINSTA
Related Pages
Juggling algorithm for array rotation
 
Balanced Parenthesis Problem
 
Remove brackets from an algebraic expression

Count the number of vowels

Remove the vowels from a String

Method 3
Output
This program is the same as above, but this time we are using the While Loop.

Run
#include <stdio.h>
#include <string.h>

// Make sure that have knowledge about ASCII
// if not please check - https://prepinsta.com/ascii-table/

int main() 
{
    char str1[100];
    printf("Please Enter any String to Toggle :  ");
    
    gets(Str1);
    int i = 0;

    while(str1[i] != '\0') {
        
        if(str1[i] >= 'a' && str1[i] <= 'z') {                    
                str1[i] = str1[i] - 32;
        }
        
        else  if(str1[i] >= 'A' && str1[i] <= 'Z') {
            str1[i] = str1[i] + 32;
        }
        
        i++;
    }

    printf("After Toggling Case of all Characters = %s", str1);
    
    return 0;
}
Please Enter any String to Toggle : PREPinsta

After Toggling Case of all Characters = prepINSTA
Method 4 (Using Recursion)
This method uses recursion in C

Run
#include <stdio.h>
#include <string.h>

// Make sure that have knowledge about ASCII
// if not please check - https://prepinsta.com/ascii-table/
int toggleString(char *str)
{
	static int i=0;
	if(str[i])
    {
        // if b/w a-z
        if(str[i] >= 65 && str[i] <= 90)
            str[i]+=32;
        
        // if b/w A-Z
        else if(str[i] >= 97 && str[i] <= 122)
            str[i]-=32;
         
        i++;
        toggleString(str);
    }  
}
int main()
{
    char str[1000];  
  
    printf("Enter the string: ");
    scanf("%[^\n]s", str);
    
    toggleString(str);
     
    printf("String After toggling ='%s'\n",str);
    
    return 0;
 }
Output
Please Enter any String to Toggle : PREPinsta

The Given String after Toggling Case of all Characters = prepINSTA
Method 5 (Using Pointers)
Run
#include <stdio.h>
#include <string.h>
 
 
int main()
{
    char str[1000], *p;  

    printf("Enter a string: ");
    gets(str);
    
    p = str;
    int i = 0;
    
    // keeps reading until we read \0
	while(*(p+i))  
    {
        if(*(p+i) >= 65 && *(p+i) <= 90)
         *(p+i)+=32;
         
        else if(*(p+i) >= 97 && *(p+i) <= 122)
         *(p+i)-=32;
         
        i++; 
 	}
 	     
    printf("Toggled String : '%s'\n", p);
    
    return 0;
}
Output
Enter a string: PrepInsta
Toggled String : 'pREPiNSTA'

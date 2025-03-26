# Vigenere Cipher
Vigenere Cipher using with different key values

# AIM:
To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:
### Step 1:
Design of Vigenere Cipher algorithnm

### Step 2:
Implementation using C or pyhton code

### Step 3:
Testing algorithm with different key values. ALGORITHM DESCRIPTION: The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a repeating keyword.

## PROGRAM:
``` C
#include <stdio.h>
#include <stdlib.h>  // For exit() function
#include <ctype.h>   // For toupper() function
#include <string.h>  // For strlen() function

void encipher();
void decipher();

int main() {
    int choice;
    while (1) {
        printf("\n1. Encrypt Text");
        printf("\n2. Decrypt Text");
        printf("\n3. Exit");
        printf("\n\nEnter Your Choice: ");
        scanf("%d", &choice);

        if (choice == 3)
            exit(0);
        else if (choice == 1)
            encipher();
        else if (choice == 2)
            decipher();
        else
            printf("Please Enter a Valid Option.\n");
    }
    return 0;  // Added return statement for the main function
}

void encipher() {
    unsigned int i, j;
    char input[50], key[10];

    printf("\n\nEnter Plain Text: ");
    scanf("%s", input);  // Removed newline for better input handling

    printf("Enter Key Value: ");
    scanf("%s", key);

    printf("Resultant Cipher Text: ");
    for (i = 0, j = 0; i < strlen(input); i++, j++) {
        if (j >= strlen(key)) {
            j = 0;
        }
        printf("%c", 65 + (((toupper(input[i]) - 65) + (toupper(key[j]) - 65)) % 26));
    }
    printf("\n");  // Added newline for output formatting
}

void decipher() {
    unsigned int i, j;
    char input[50], key[10];
    int value;

    printf("\n\nEnter Cipher Text: ");
    scanf("%s", input);  // Removed newline for better input handling

    printf("Enter the Key Value: ");
    scanf("%s", key);

    printf("Resultant Plain Text: ");
    for (i = 0, j = 0; i < strlen(input); i++, j++) {
        if (j >= strlen(key)) {
            j = 0;
        }

        // Calculate the decrypted character value
        value = (toupper(input[i]) - 65) - (toupper(key[j]) - 65);
        if (value < 0) {
            value += 26;  // Correct for negative values in circular shift
        }
        printf("%c", 65 + (value % 26));
    }
    printf("\n");  // Added newline for output formatting
}
```

## Output:
![exp 4ss](https://github.com/user-attachments/assets/650e5f00-3304-4fd6-b581-106382e25ded)

## Result:
The program for Vigenere Cipher is executed successfully.

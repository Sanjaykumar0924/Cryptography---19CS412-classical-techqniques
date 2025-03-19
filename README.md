AIM:
To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.

DESIGN STEPS:
Step 1:
Design of Caeser Cipher algorithnm

Step 2:
Implementation using C or pyhton code

Step 3:
In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the
scheme, A = 0, B = 1, Z = 25.
Encryption of a letter x by a shift n can be described mathematically as, En(x) = (x + n) mod26
Decryption is performed similarly, Dn (x)=(x - n) mod26

PROGRAM:
PROGRAM: CaearCipher.
```
#include <stdio.h>
#include <string.h>

int main()
{ int key; char s[1000];

printf("Enter a plaintext to encrypt:\n");
fgets(s, sizeof(s), stdin);
printf("Enter key:\n");
scanf("%d", &key);

int n = strlen(s);

for (int i = 0; i < n; i++) 
{
    char c = s[i];
    if (c >= 'a' && c <= 'z') 
    {
        s[i] = 'a' + (c - 'a' + key) % 26;
    }
    else if (c >= 'A' && c <= 'Z')
    {
        s[i] = 'A' + (c - 'A' + key) % 26;
    }
}
printf("Encrypted message: %s\n", s);

for (int i = 0; i < n; i++)
{
    char c = s[i];
    if (c >= 'a' && c <= 'z') 
    {
        s[i] = 'a' + (c - 'a' - key + 26) % 26; 
    }
    else if (c >= 'A' && c <= 'Z')
    {
        s[i] = 'A' + (c - 'A' - key + 26) % 26; 
    }
}
printf("Decrypted message: %s\n", s);

return 0;
}
```

OUTPUT:
![exp 1 ss](https://github.com/user-attachments/assets/10cd4be3-2c35-4d9e-9fc7-1b18ffedb961)


RESULT:
The program is executed successfully

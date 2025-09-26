## Exp:1 IMPLEMENTATION OF CAESER CIPHER 

## AIM: 
To encrypt and decrypt the given message by using Caeser Cipher encryption algorithm. 
  
 ## ALGORITHM: 
1. Calculate the length of the plaintext. 
2. For each character in the plaintext:  
 a. Add the key to the character to get the cipher character.  
 b. If the result exceeds 'Z' for uppercase or 'z' for lowercase, subtract 26 to wrap within the  alphabet.  
3. Display the encrypted text.  
4. For decryption, subtract the key from each character of the ciphertext.  
 a. If the result is less than 'A' for uppercase or 'a' for lowercase, add 26 to wrap within the  alphabet.  
5. Display the decrypted text.  

## PROGRAM: 
````
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main() {
    char text[100], ch;
    int key, i;
    printf("Enter a plain text: ");
    fgets(text, sizeof(text), stdin);
    
    text[strcspn(text, "\n")] = '\0';
    
    printf("Enter key (integer): ");
    scanf("%d", &key);

    printf("Encrypted text: ");
    for (i = 0; text[i] != '\0'; ++i) {
        ch = text[i];

        if (isalpha(ch)) {
            char base = isupper(ch) ? 'A' : 'a';
            ch = ((ch - base + key) % 26 + 26) % 26 + base; 
        }

        printf("%c", ch);
    }

    printf("\n");

    printf("Encryption complete.\n");

    return 0;
}
````

## OUTPUT: 

<img width="732" height="429" alt="image" src="https://github.com/user-attachments/assets/7bf3a08a-a048-49a3-9c03-e799a102fd3e" />



## RESULT: 
The program implementing the Caesar cipher for encryption and decryption has been successfully  executed, and the results have been verified.

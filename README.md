# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>

char* encrypt(char text[], int s) {
    static char result[100];
    int i;
    
    for (i = 0; i < strlen(text); i++) {
        char char_ = text[i];
        
        if (char_ >= 'A' && char_ <= 'Z') {
            result[i] = (char)(((int)char_ + s - 65) % 26 + 65);
        } else if (char_ >= 'a' && char_ <= 'z') {
            result[i] = (char)(((int)char_ + s - 97) % 26 + 97);
        } else {
            result[i] = char_;
        }
    }
    result[i] = '\0';
    return result;
}

char* decrypt(char text[], int s) {
    static char result[100];
    int i;
    
    for (i = 0; i < strlen(text); i++) {
        char char_ = text[i];
        
        if (char_ >= 'A' && char_ <= 'Z') {
            result[i] = (char)(((int)char_ - s - 65 + 26) % 26 + 65);
        } else if (char_ >= 'a' && char_ <= 'z') {
            result[i] = (char)(((int)char_ - s - 97 + 26) % 26 + 97);
        } else {
            result[i] = char_;
        }
    }
    result[i] = '\0';
    return result;
}

int main() {
    char text[100];
    int s;
    scanf("%s",text);
    scanf("%d",&s);
    printf("Text: %s\n", text);
    printf("Shift: %d\n", s);
    printf("Cipher: %s\n", encrypt(text, s));
    printf("Decrypted: %s\n", decrypt(encrypt(text, s), s));
    
    return 0;
}
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/8e37be7d-1c8a-4792-aeff-d02941ad1a32)


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.

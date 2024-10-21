# Caesar-Cipher---Encryption-and-Decryption

## Aim
To Implement the Caeser Cipher Encryption and Decryption ALgorithm using C program.

## Algorithm

1. Input Message and Key: Read the message and key from the user.

2. Iterate Over Characters: Loop through each character in the message.

3. Check Character Type: Ensure the character is alphanumeric.

4. Encrypt/Decrypt Character:
   
      Encrypt: Shift each character forward using the key.
   
      Decrypt: Shift each character backward using the key.

6. Validate Input: Handle non-alphanumeric characters by showing an error.

7. Display Result: Print the encrypted or decrypted message.

## Program

### Encryption
```c
#include <stdio.h>
#include <ctype.h>
int main()
{
char text[500], ch;
int key;
printf("Enter a message to encrypt: ");
scanf("%s", text);
printf("Enter the key: ");
scanf("%d", &key);
for (int i = 0; text[i] != '\0'; ++i) {
ch = text[i];
if (isalnum(ch))
{
if (islower(ch))
{
ch = (ch - 'a' + key) % 26 + 'a';
}
else if (isupper(ch))
{
ch = (ch - 'A' + key) % 26 + 'A';
}
else if (isdigit(ch))
{
ch = (ch - '0' + key) % 10 + '0';
}
text[i] = ch;
}
else {
printf("Invalid character '%c' found. Only alphanumeric characters are allowed.\n", ch);
return 1;
}
}
printf("Encrypted message: %s\n", text);
return 0;
}
```
### Decryption
```c
#include <stdio.h>
#include <ctype.h>
int main()
{
char text[500], ch;
int key;
printf("Enter a message to decrypt: ");
scanf("%s", text);
printf("Enter the key: ");
scanf("%d", &key);
for (int i = 0; text[i] != '\0'; ++i)
{
ch = text[i];
if (isalnum(ch))
{
if (islower(ch))
{
ch = (ch - 'a' - key + 26) % 26 + 'a';
}
else if (isupper(ch))
{
ch = (ch - 'A' - key + 26) % 26 + 'A';
}
else if (isdigit(ch))
{
ch = (ch - '0' - key + 10) % 10 + '0';
}
text[i] = ch;
}
else
{
printf("Invalid character '%c' found. Only alphanumeric characters are allowed.\n", ch);
return 1;
}
}
printf("Decrypted message: %s\n", text);
return 0;
}
```
## Output

### Encryption
![image](https://github.com/user-attachments/assets/a237f719-ce68-4f30-abf9-60c1f61e5c46)

### Decryption
![image](https://github.com/user-attachments/assets/769315ea-0124-410e-9bf6-ba66c2849e38)


## Result

Thus To Implement the Caeser Cipher Encryption and Decryption ALgorithm using C program is done successfully.

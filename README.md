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

```java
import java.util.Scanner;

public class CaesarCipher {

  String encode(String plainText, int key) {
    char[] cipherTextArray = plainText.toCharArray();
    int len = cipherTextArray.length;
     for (int i = 0 ; i < len ; i++) {
       char letter = cipherTextArray[i];
       if(Character.isLowerCase(letter))
          cipherTextArray[i] = (char)('a' + ((letter - 'a' + key) % 26));
       else if (Character.isUpperCase(letter))
          cipherTextArray[i] = (char)('A' + ((letter - 'A' + key) % 26));
        else
          continue;
     } 
     return new String(cipherTextArray);
  }

  String decode(String cipherText, int key) {
      char[] plainTextArray = cipherText.toCharArray();
      int len = plainTextArray.length;
      for (int i = 0 ; i < len ; i++) {
        char letter = plainTextArray[i];
        if(Character.isLowerCase(letter))
            plainTextArray[i] = (char)('a' + (letter - 'a' - key + 26) % 26);  
        else if (Character.isUpperCase(letter))
            plainTextArray[i] = (char)('A' + (letter - 'A' - key+ 26) % 26);
        else  
          continue;
      }
      return new String(plainTextArray);
  }

  public static void main(String args[]) {
      String plainText, cipherText;
      int key = 1;
      Scanner sc = new Scanner(System.in);
      System.out.print("Enter the plain text to encrypt : ");
      plainText = sc.nextLine();
      System.out.print("Enter the key : ");
      key = sc.nextInt();
      CaesarCipher ccObj = new CaesarCipher();
      cipherText = ccObj.encode(plainText, key);
      System.out.println("Encrypted text : " + cipherText);
      if (plainText.equals(ccObj.decode(cipherText, key))) {
        System.out.println("Decode Successful\nDecoded Text : " + plainText);
      } else {
        System.out.println("Decode Failed\n");
      }
      System.out.println("Implementation of CaesarCipher in java is done");
      sc.close();
  }
}
```
## OUTPUT:
<img width="822" height="643" alt="image" src="https://github.com/user-attachments/assets/9e615df8-686a-4186-a9c4-256bab86fe84" />


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.

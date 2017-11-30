# Simple Encryption using C# using XOR technique!

## Introduction

Passwords are essential thing in virtual world, it is the thing which keeps you safe, If someone else gains access to your account, they may cause you a great deal of trouble - perhaps deleting your files,  hack other systems or may stolen crucial data from your system.
so while development a big/small and web/windows application you need to keep password for your account. A password with a plain text is always a danger since it can be easily Move stealthily by someone so, we need to make our plain text password to some tricky thing and thus here we need some type of 'ENCRYPTION'.

![encryption-key](http://1.bp.blogspot.com/-YqpcO3B-gA0/U6AG313rwQI/AAAAAAAABjI/pfzmbXe_d1Y/s1600/encryption-key.jpg)

Many times we need to encrypt the string in our application, it may be used for login password, transaction password, secret key etc. 
In this post, I will explain how to encrypt a string using C# with XOR encryption technique
.NET provide inbuilt encryption technique using 'System.Cryptography' namespace and various in-built encryption algorithms like,

1. AES
2. Blowfish
3. DES
4. Triple DES
5. Serpent
6. Twofish
7. Camellia
8. CAST-128
9. IDEA,RC2,RC5,SEED,Skipjack,TEA,XTEA etc

Here we go for some different technique apart from above algorithms

**XOR encryption (exclusive disjunction (XOR) operation):**

The XOR operator is extremely common and execute with the help of binary operations.
One of the cool things about XOR encryption is that when you apply it twice, you get back the original string
In this encryption we convert our Plain text and key to 8-bit ASCII format and then apply X-OR operation on them and same thing is done for decryption.

**Let's Code:**

Things we need : C# windows/web application
Write a function in C# which accept a plain text and a key to encrypt the text
see below snippet

```javascript
public string EncryptDecrypt(string szPlainText, int szEncryptionKey)  
     {  
       StringBuilder szInputStringBuild = new StringBuilder(szPlainText);  
       StringBuilder szOutStringBuild = new StringBuilder(szPlainText.Length);  
       char Textch;  
       for (int iCount = 0; iCount < szPlainText.Length; iCount++)  
       {  
         Textch = szInputStringBuild[iCount];  
         Textch = (char)(Textch ^ szEncryptionKey);  
         szOutStringBuild.Append(Textch);  
       }  
       return szOutStringBuild.ToString();  
     }  
```

Now we have ready with the code in which we have accept the plain text and key to encrypt the text. Finally we have apply XOR operation on plain text
Above function will give you Encrypted string and Same function with same key will return your Decrypted string
I have call above function and pass plain text and a key to it.

```javascript
 txtEncryptedText.Text = EncryptDecrypt(txtPlainText.Text, 200);  
```

I got following result, see below snaps

![output](http://1.bp.blogspot.com/-aqnhvT_o_fw/U6ADXa7Uh9I/AAAAAAAABi8/ZrVmnNaMDD4/s1600/XOR1.jpg)

Now to Decrypt the encrypted string just call same function and pass the encrypted string to it (Do not change encryption key)
Now this simple encryption is ready to use anywhere you want.

Thanks
koolprasad

## WhiteHat Crew CTF 2022

### Reversing
#### 1) Baby Ransom

Question: A client sent to you his folder that can't be open, get the flag from one of the files.

Answer:

Got r4nsom.py script that will encrypt the files. The fernet module of the cryptography package has inbuilt functions for the generation of the key, encryption of plaintext into ciphertext, and decryption of ciphertext into plaintext using the encrypt and decrypt methods respectively. The fernet module guarantees that data encrypted using it cannot be further manipulated or read without the key. [source](https://www.geeksforgeeks.org/fernet-symmetric-encryption-using-cryptography-module-in-python/)

![image](https://user-images.githubusercontent.com/84785099/147880978-0169a67a-de80-4098-973e-353b8bf2df8d.png)

We can decrypt the file if we know the encryption key which is the `Fernet.generate_key()`. There is a passkey file which is the encryption key for the encrypted files found in the `Azman's HDD` folder

![image](https://user-images.githubusercontent.com/84785099/147879642-e9b802c8-cb22-4745-a8c7-e916f2c85cd8.png)

One of the file in `Azman's HDD` folder contain flag, decrypt it and you'll get the flag. There is a large number of files in the directory, so we can sort them by file size as the different one is assumed as the flag file. So, we have `2360 ./IMG_043` as the possible flag file.

![image](https://user-images.githubusercontent.com/84785099/147879872-2c903c3f-6491-44b0-b9f7-4762d7dedbf3.png)

Here is the simple decrypter to decrypt the files back.

![image](https://user-images.githubusercontent.com/84785099/147879743-45826649-3900-45a6-942e-ddd63402e3ce.png)

---

### Cryptography
#### 1) Beginner Cryptography

Question: > Decode this base64:
> 
> YmFzZTY0X2lzX292ZXJyYXRlZA==
> 
> Enwrap it in WHC{} like this:-
> 
> WHC{your_decoded_text_here}

Answer: WHC{base64_is_overrated}

#### 2) anencephaly

Question: What is this pokemon? .

Answer: 

1. Base64 decode the file

![image](https://user-images.githubusercontent.com/84785099/147880337-7147c9af-8cde-4bbe-a1d4-9d42a8cd5b62.png)

2. Interpret with brainfuck language

![image](https://user-images.githubusercontent.com/84785099/147880366-6699d1fd-612a-49ac-96d9-5efd1146e1f1.png)

3. Base64 decode again

 ![image](https://user-images.githubusercontent.com/84785099/147880408-8ff093cc-5c49-4dfa-88a4-486b1da91eb2.png)

#### 3) Botak

Question: An old uncle is so tired trying to get his password came to you, he forgot his password. Can you try to brute force his password back?

Answer: Given `botak.py` script is actually a Caesar Cipher encoder which contain a hint for the flag as highlighted below.

![image](https://user-images.githubusercontent.com/84785099/147880594-9d1d8345-bfaf-4d2d-8755-4e39f23e7c81.png)

Simply decode it online

![image](https://user-images.githubusercontent.com/84785099/147880711-197cae45-2af4-4f9f-b124-f1de5959d20b.png)

#### 4)  XORing

Question: XOR is one of the common way to obfuscate programs and malware from being detect by Anti-Virus Vendor or Yara Rules. By hiding itself from showing and match a certain ruleset, it can flag as malicious file easily to be alert and remove hence XOR is one of the technique used.

![image](https://user-images.githubusercontent.com/84785099/147880859-50a74ada-106c-4818-a622-08d63bb8ee2c.png)

Answer:

![image](https://user-images.githubusercontent.com/84785099/147880932-32ea1b65-bdb9-427a-8695-9f7d36097795.png)

---

### Forensic
#### 1) Beginner Forensics

Question: There is supposed to be less than 10 items. Click on everything and find a human readable text.
What does the text said, and what number is the item number is the text? How many rows of the "No." column
Flag Format i.e : WHC{36:Hello it's me}

Answer: WHC{4:What, me worry?}

![image](https://user-images.githubusercontent.com/84785099/147881143-4ee32d3d-d62f-4e00-8d27-e19dba6e444d.png)

#### 2) Penceroboh-1

Question: WHC{user:pass} , user starts with: a

Answer: Packet no 163

![image](https://user-images.githubusercontent.com/84785099/147881226-ee864379-2897-4c46-b944-e7f733f81394.png)

#### 3) Penceroboh-2

Question: WHC{user:pass}, user starts with: b

Answer: Packet no 60

![image](https://user-images.githubusercontent.com/84785099/147881280-d838d9de-fe77-4246-a245-4f85058bd37b.png)

#### 4) Penceroboh-3

Question: 3 Credentials, WHC{user:pass}

Answer: Packet no 138

![image](https://user-images.githubusercontent.com/84785099/147881325-765bb18c-fd2f-4a4f-8fb7-dd23e70920f2.png)

#### 5) topiputih

Question: Apa makna topi putih?

Answer: Strings topi.png

![image](https://user-images.githubusercontent.com/84785099/147881379-0fcd089f-eccb-4744-ad68-2ad4ec05e567.png)

#### 5) A walk in the park

Question: Classical! Easy just like a walk in the park.

Answer: Go to https://futureboy.us/stegano/decode.pl and upload meme.jpg

![image](https://user-images.githubusercontent.com/84785099/147881477-c2d441d4-3b03-40aa-b090-82cc468c6f9f.png)

---

### Malware
#### 1) Malware A - 1 

Question: A "not-so-good" developer brought aboard disaster to a common programming language and you guessed it, someone exploit it to create malware.
What is the file SHA256 hash? WHC{SHA256}

Answer: sha256sum config

![image](https://user-images.githubusercontent.com/84785099/147881581-02623801-d376-423b-8c30-1d1b6b81f232.png)

#### 2) Malware A - 2

Question: What is the threat name, hosts and classification? Format : WHC{threat name|hosts|classification}

Answer: Based on VirusTotal info

![image](https://user-images.githubusercontent.com/84785099/147881761-31e65982-0e3c-4a14-9428-e999217365a6.png)




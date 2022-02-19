
### Cracking SH key passphrase with john

```bash

$ cp /usr/share/john/ssh2john.py /home/kali/Downloads
$ python3 ssh2john.py idrsa.id_rsa > output_hash
$ john --wordlist=/usr/share/wordlists/rockyou.txt output_hash

Using default input encoding: UTF-8
Loaded 1 password hash (SSH, SSH private key [RSA/DSA/EC/OPENSSH 32/64])
Cost 1 (KDF/cipher [0=MD5/AES 1=MD5/3DES 2=Bcrypt/AES]) is 0 for all loaded hashes
Cost 2 (iteration count) is 1 for all loaded hashes
Will run 4 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
delicious        (idrsa.id_rsa)     
1g 0:00:00:00 DONE (2022-01-22 22:32) 100.0g/s 393600p/s 393600c/s 393600C/s zamora..delicious
Use the "--show" option to display all of the cracked passwords reliably
Session completed.


```

Decrypting gpg with a secret key

```bash
┌──(kali㉿kali)-[~/Desktop/tryhackme]
└─$ ls                                                                            gpg.zip  message.gpg  tryhackme.key
                          
┌──(kali㉿kali)-[~/Desktop/tryhackme]
└─$ gpg --import tryhackme.key -d message.gpg
gpg: /home/kali/.gnupg/trustdb.gpg: trustdb created
gpg: key FFA4B5252BAEB2E6: public key "TryHackMe (Example Key)" imported
gpg: key FFA4B5252BAEB2E6: secret key imported
gpg: can't open '-d': No such file or directory
gpg: Total number processed: 1
gpg:               imported: 1
gpg:       secret keys read: 1
gpg:   secret keys imported: 1
                         
┌──(kali㉿kali)-[~/Desktop/tryhackme]
└─$ gpg -d message.gpg                                                                                     2 ⨯
gpg: encrypted with 1024-bit RSA key, ID 2A0A5FDC5081B1C5, created 2020-06-30
      "TryHackMe (Example Key)"
You decrypted the file!
The secret word is Pineapple.
```
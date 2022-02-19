**How to Use SSH Public Key Authentication**
https://serverpilot.io/docs/how-to-use-ssh-public-key-authentication/

---

**How Public Key Authentication Works**
1.  Generate a key pair.
2.  Give someone (or a server) the public key.
3.  Later, anytime you want to authenticate, the person (or the server) asks you to prove you have the private key that corresponds to the public key.
4.  You prove you have the private key.
---
**1. Generate an SSH Key Pair**
```bash
ssh-keygen
```

**2.  Configure an SSH/SFTP User for Your Key**

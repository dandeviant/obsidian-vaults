Source of references:
- https://computingforgeeks.com/how-to-install-and-configure-openldap-server-on-debian/
- https://likegeeks.com/linux-ldap-server/
---

Step 1: Update Debian server

It is always a good practice to keep the sources updated before installing anything.
Don't forget to restart your machine in order for the updates to take place.

>```bash
>$ sudo apt-get update && sudo apt upgrade
>$ sudo reboot
>```

---

Step 2: Installing OpenLDAP


> ```bash
> 
>$ sudo apt -y install slapd ldap-utils

- You will be prompted with Administrator password and confirmation
- If installation succeeded, a slapcat command should provide OpenLDAP server details

sample of output
>```bash
dn: dc=computingforgeeks,dc=com 
objectClass: top objectClass: dcObject 
objectClass: organization 
o: computingforgeeks.com 
dc: computingforgeeks 
structuralObjectClass: organization 
entryUUID: 3380a11a-587c-1039-8fb1-a76b7240a677 
creatorsName: cn=admin,dc=computingforgeeks,dc=com 
createTimestamp: 20190821162641Z 
entryCSN: 20190821162641.076360Z#000000#000#000000 
modifiersName: cn=admin,dc=computingforgeeks,dc=com 
modifyTimestamp: 20190821162641Z 
>
dn: cn=admin,dc=computingforgeeks,dc=com 
objectClass: simpleSecurityObject 
objectClass: organizationalRole 
cn: admin 
description: LDAP administrator 
userPassword:: e1NTSEF9eDN2SUVtUnRZMUFjeHZuREtMaDlwdjU5c3dMZkFaWmM= 
structuralObjectClass: organizationalRole 
entryUUID: 3380e3fa-587c-1039-8fb2-a76b7240a677 
creatorsName: cn=admin,dc=computingforgeeks,dc=com 
createTimestamp: 20190821162641Z 
entryCSN: 20190821162641.078129Z#000000#000#000000 
modifiersName: cn=admin,dc=computingforgeeks,dc=com 
modifyTimestamp: 20190821162641Z
>
>```

---

Step 3: Add base dn for Users and Groups

- Create a file named basedn.ldif with contents as below: 

>```bash
>dn: ou=people,dc=computingforgeeks,dc=com 
>objectClass: organizationalUnit 
>ou: people 
>
>dn: ou=groups,dc=computingforgeeks,dc=com 
>objectClass: organizationalUnit 
>ou: groups
>```

- Apply configurations

>```bash
> $ sudo ldapadd -x -D cn=admin,dc=computingforgeeks,dc=com -W -f basedn.ldif
>```

Sample output
>```bash
> Enter LDAP Password: 
> adding new entry "ou=people,dc=computingforgeeks,dc=com" 
> adding new entry "ou=groups,dc=computingforgeeks,dc=com"
>```

---
Step 4: Add User Accounts and Groups

- Generate passwored for user account to add

>```bash
>$ sudo slappasswd
>New password: 
>Re-enter new password:
>{SSHA}5D94oKzVyJYzkCq21LhXDZFNZpPQD9uE
>```

- Create ldif file for adding users:

> ```bash
> 
> $ nano ldapusers.ldif
>  dn: uid=jmutai,ou=people,dc=computingforgeeks,dc=com 
>  objectClass: inetOrgPerson
>  objectClass: posixAccount 
>  objectClass: shadowAccount 
>  cn: Josphat 
>  sn: Mutai 
>  userPassword: {SSHA}5D94oKzVyJYzkCq21LhXDZFNZpPQD9uE
>  loginShell: /bin/bash 
>  homeDirectory: /home/testuser 
>  uidNumber: 3000 
>  gidNumber: 3000
> ```

- Replace ``jmutai`` with the username to add
- ``dc=computingforgeeks,dc=com`` with your correct domain values.
- ``cn`` & ``sn`` with your user details
- ``{SSHA}5D94oKzVyJYzkCq21LhXDZFNZpPQD9uE`` with your hashed password generated.

- Apply config

> ```bash
> sudo ldapadd -x -D cn=admin,dc=computingforgeeks,dc=com -W -f ldapusers.ldif
> Enter LDAP Password: 
> adding new entry "uid=jmutai, ou=people, dc=computingforgeeks, dc=com"
> 
> ```

- A group is added in similar way. Do the same of group. Create ldif file:

>```bash
>$ cat ldapgroups.ldif 
>dn: cn=_jmutai_,ou=groups,dc=computingforgeeks,dc=com 
>objectClass: posixGroup 
>cn: jmutai 
>gidNumber: 3000 
>memberUid: jmutai 
>
>$ sudo ldapadd -x -D cn=admin,dc=computingforgeeks,dc=com -W -f ldapgroups.ldif 
>
>Enter LDAP Password: 
>adding new entry "cn=jmutai, ou=groups, dc=computingforgeeks, dc=com"
>```

---
Step 5: Install LDAP Account Manager

We’ll install and use [LDAP Account Manager](https://www.ldap-account-manager.org/lamcms/) as our OpenLDAP Server graphical management dashboard. LDAP Account Manager (LAM) is a web frontend for managing entries (e.g. users, groups, DHCP settings) stored in an LDAP director

- Download the latest release of [ldap account manager deb package](https://www.ldap-account-manager.org/lamcms/releases):

>```bash
>wget http://prdownloads.sourceforge.net/lam/ldap-account-manager_7.7-1_all.deb sudo apt install -f ./ldap-account-manager_7.7-1_all.deb
>```

---
Step 6: Configure LDAP Account Manager

- Access  LDAP Account Manager web interface from a trusted machine network on
>```bash
>http://(server’s hostname or IP address)/lam
>```
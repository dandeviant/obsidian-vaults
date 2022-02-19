Will use OpenLDAP Directory Services

>```bash
>sudo apt install slapd ldap-utils
>```

- Enter administrator password and confirmation

>```bash
>sudo dpkg-reconfigure slapd
>```

- Omit OpenLDAP server configuration? ==No==
- DNS domain name = anything.net
- Organization name = anything
- Enter admin password and confirm

- Database backend to use: ==MDB==
- Do you want the database to be removed when slapd is purged? ==No==
- Move old database? ==Yes==

>```bash
>sudo tree /etc/ldap/slapd.d
>
>sudo nano add_entries.ldif
>```

Enter the following into add_entries.ldif:

> ```bash
> dn: ou=Employee, dc=test,dc=local
> objectclass: organizationalUnit
> ou: Employee
> 
>dn: ou:groups,dc=test,dc=local
>objectClass: organizationalUnit
>ou: Groups
>
>dn: cd=developers, dc=test,dc=local
>objectClass: posixgroup
>cn: developers
>gidNumber: 5000
>
>dn: uid=freddy,ou=Employee,dc=test,dc=local
>ObjectClass: onetOrgPerson
>Objectclass: posixAccount
>ObjectClass: shadowAccount
>uid: daniel
>sn: md
>givenName: daniel
>displayName: Daniel Md
>uidNumber: 10000
>gidNumber: 5000
>userPassword: 123
>loginShell: /bin/bash
>homeDirectory: /home/daniel/
> ```

>```bash
> ldapadd -x -D cn=admin,dc=local,dc=local -W -f add_entries.ldif
>
> Enter LDAP Password:
>```

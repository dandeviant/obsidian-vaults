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
> dn: ou=Employee, dc=practice,dc=net
> objectclass: organizationalUnit
> ou: Employee
> 
>dn: ou:groups,dc=practice,dc=net
>objectClass: organizationalUnit
>ou: Groups
>
>dn: cd=developers, ou=practice,dc=net
>objectClass: posixgroup
>cn: developers
>gidNumber: 5000
>
> dn: uid=freddy, ou=Employee,dc=practice,dc=net
> ObjectClass: onetOrgPerson
> Objectclass: posixAccount
> ObjectClass: shadowAccount
> uid: freddy
> sn: smith
>givenName: freddy
>displayName: Freddy Smith
>uidNumber: 10000
>gidNumber: 5000
>userPassword: 123
>loginShell: /bin/bash
>homeDirectory: /home/freddy/
> ```

>```bash
> ldapadd -x -D cn=admin,dc=practice,dc=net -W -f add_entries.ldif
>
> Enter LDAP Password:
>```

```bash
[recon-ng][thmredteam] > db query select * from domains
[*] No data returned.
[recon-ng][thmredteam] > db insert domains
domain (TEXT): thmredteam.com
notes (TEXT): 
[*] 1 rows affected.
[recon-ng][thmredteam] > db query select * from domains

  +---------------------------------------+
  |     domain     | notes |    module    |
  +---------------------------------------+
  | thmredteam.com |       | user_defined |
  +---------------------------------------+

[*] 1 rows returned
[recon-ng][thmredteam] > marketplace search hosts-domains
[*] Searching module index for 'hosts-domains'...

  +----------------------------------------------------------------------------------+
  |                Path               | Version |     Status    |  Updated   | D | K |
  +----------------------------------------------------------------------------------+
  | recon/hosts-domains/migrate_hosts | 1.1     | not installed | 2020-05-17 |   |   |
  +----------------------------------------------------------------------------------+

  D = Has dependencies. See info for details.
  K = Requires keys. See info for details.

[recon-ng][thmredteam] > marketplace search censys_email_address
[*] Searching module index for 'censys_email_address'...

  +----------------------------------------------------------------------------------------------+
  |                      Path                     | Version |     Status    |  Updated   | D | K |
  +----------------------------------------------------------------------------------------------+
  | recon/companies-contacts/censys_email_address | 2.0     | not installed | 2021-05-11 | * | * |
  +----------------------------------------------------------------------------------------------+

  D = Has dependencies. See info for details.
  K = Requires keys. See info for details.

[recon-ng][thmredteam] > marketplace info censys_email_address

  +-----------------------------------------------------------------------------------------------------------------------------------+
  | path          | recon/companies-contacts/censys_email_address                                                                     |
  | name          | Censys emails by company                                                                                          |
  | author        | Censys Team                                                                                                       |
  | version       | 2.0                                                                                                               |
  | last_updated  | 2021-05-11                                                                                                        |
  | description   | Retrieves email addresses from the TLS certificates for a company. Updates the 'contacts' table with the results. |
  | required_keys | ['censysio_id', 'censysio_secret']                                                                                |
  | dependencies  | ['censys>=2.0.0']                                                                                                 |
  | files         | []                                                                                                                |
  | status        | not installed                                                                                                     |
  +-----------------------------------------------------------------------------------------------------------------------------------+

[recon-ng][thmredteam] > 

```

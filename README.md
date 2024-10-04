# Bind9 Management Script

Bind9 management script to simplify adding and removing records via nsupdate

## Features

- Tries to understand what you're asking for
  - Searches input to match short reference to zone names
- Can add A, NS, and PTR records so far
- Can list existing entries of specific type from selected zone

## Use

- Requires: nsupdate and dig
  - The nsupdate key file can be created by removing all other sections from a named.conf file leaving only the key "whatever" section containing the algoithm and secret.
- Expects to talk to a server 
- Note: Most testing has been done against an IP on the same host, but any system which can perform zone transfers and is permitted by IP to perform domain updates should function.
- Parameters can be specified in any order
- Default is 'add' and 'A' record

```sh
# Sample call to add ns1 A and NS records to domain foo.bar.local for IP 192.168.1.10
dnsedit ns1 192.168.1.10 foo.bar.local
dnsedit NS ns1 foo.bar.local
```

## Future Updates (soon)

- Help menu
- Deleting entries
- Adding CNAME entries
- Better logic and more checks
- Adding PTR together with A and override to not do so

### Later updates (probably not soon - so if you want to fix this and do a PR, awesome)
- Adding MX/SOA entries 
- Checking if entries exist to delete/replace or prompt for their replacement


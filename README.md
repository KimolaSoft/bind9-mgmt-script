# Bind9 Management Script

Bind9 management script to simplify adding and removing records via nsupdate

## Features

- Tries to understand what you're asking for
  - Searches input to match short reference to zone names (based on BASE name)
- Supports A, NS, PTR, CNAME, MX, and TXT records
- Can list existing entries of specific type from selected zone
- Non-interactive mode for scripting (`-y` flag)
- Automatic PTR record creation when adding A records (use `noptr` to disable)
- Help menu available (`-?` or `-h` or `--help`)

## Use

- Requires: nsupdate and dig
  - The nsupdate key file can be created by removing all other sections from a named.conf file leaving only the key "whatever" section containing the algoithm and secret.
- Expects to talk to a server 
- Note: Most testing has been done against an IP on the same host, but any system which can perform zone transfers and is permitted by IP to perform domain updates should function. The named.conf file is parsed, so a copy of it would be required on the remote system, but that path is configurable
- Parameters can be specified in any order
- Default is 'add' and 'A' record

```sh
# Sample call to add ns1 A and NS records to domain foo.bar.local for IP 192.168.1.10
dnsedit ns1 192.168.1.10 foo
dnsedit NS ns1 foo

# Delete a record (non-interactive)
dnsedit -y del ns1 foo

# List all A records in a zone
dnsedit list foo

# Add MX record
dnsedit mx mail foo

# Add TXT record
dnsedit txt myhost "v=spf1 include:_spf.example.com ~all" foo

# Add A record without auto-PTR
dnsedit -no-ptr ns1 192.168.1.10 foo

# Show help
dnsedit -h
```

## Future Updates (soon)

- Better logic and more checks
- Entry replacement/overwrite option

### Later updates (probably not soon - so if you want to fix this and do a PR, awesome)
- Adding SOA entries 
- Checking if entries exist to delete/replace or prompt for their replacement
- IPv6/AAAA records - NOT PLANNED at this time

## Support / Donation / Thanks options

- BTC / Bitcoin Network: 335tkaVGpoe9Ff44XcPzEEJfDW5aUnsz3G
- BTC / Ethereum Network: 0x2Ad50f6EcdE05C5e9c0E5F948D7F8Cc78A2806b1
- ETH / Ethereum Network: 0xfb80606A020cd777E821ea3515EcFE3e58508aC8

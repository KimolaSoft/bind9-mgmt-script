# Bind9 Management Script

Bind9 management script to simplify adding and removing records via nsupdate

## Features

- Tries to understand what you're asking for
  - Searches input to match short reference to zone names
- Can add A, NS, and PTR records so far
- Can list existing entries of specific type from selected zone

## Future Updates (soon)

- Help menu
- Deleting entries
- Adding CNAME entries
- Better logic and more checks
- Adding PTR together with A and override to not do so

### Later updates (probably not soon - so if you want to fix this and do a PR, awesome)
- Adding MX/SOA entries 
- Checking if entries exist to delete/replace or prompt for their replacement


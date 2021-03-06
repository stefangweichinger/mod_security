mod_security
============
This repository contains [mod_security](https://modsecurity.org/) rules for ownCloud and all shipped applications.

This rules are following a positive security model, this means that only requests that are known to be valid are accepted and everything else is rejected.

| Folder | Description |
|-----|------------|
| /rules/ | Contains stable rules.
| /experimental/ | Contains experimental rules which should only be used carefully in production.
| /hotfix/ | Contains hotfixes for security issues. - Please use them only if you have to, updating the instance is often a better idea.
| /kiddy_blocker/ | Rules to block attackers that are trying to exploit known vulnerablities.

## Supported versions
- ownCloud 5.0
  - ownCloud 5.0.6

## FAQ
### What webservers are tested?
We've tested the rules under Apache 2.2 and mod_security 2.6

### Installation

Without reverse proxy:
```
Include "/mod_security/config/normal.conf"
Include "/mod_security/kiddy_blocker/*.conf"
Include "/mod_security/rules/*.conf"
```

With reverse proxy (``X-Forwarded-For``):
```
Include "/mod_security/config/reverse.conf"
Include "/mod_security/kiddy_blocker/*.conf"
Include "/mod_security/rules/*.conf"
```

### Does this really prevent security issues?
Yup! - About 90% of the past security issues in ownCloud would have been prevented using this rules.

## Licensing
AGPLv3
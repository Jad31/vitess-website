---
title: CreateCRL
series: vttlstest
commit: 6eddcaeac58bed83ebfa3b9ada903ddc8ff36ff6
---
## vttlstest CreateCRL

Create certificate revocation list

### Synopsis

Create certificate revocation list

```
vttlstest CreateCRL [--root <dir>] <server>
```

### Examples

```
CreateCRL --root /tmp mail.mycoolsite.com
```

### Options

```
  -h, --help   help for CreateCRL
```

### Options inherited from parent commands

```
      --root string   root directory for all artifacts (default ".")
```

### SEE ALSO

* [vttlstest](../)	 - vttlstest is a tool for generating test certificates, keys, and related artifacts for TLS tests.


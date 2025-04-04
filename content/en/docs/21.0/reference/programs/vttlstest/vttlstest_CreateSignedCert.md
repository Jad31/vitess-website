---
title: CreateSignedCert
series: vttlstest
commit: d9bc0da8c46a6f69fec4dd3d50187501d1d6268b
---
## vttlstest CreateSignedCert

Create signed certificate

### Synopsis

Create signed certificate

```
vttlstest CreateSignedCert [--root <dir>] [--parent <name>] [--serial <serial>] [--common-name <CN>] <cert name>
```

### Examples

```
CreateSignedCert --root /tmp --common-name mail.mysite.com --parent mail.mycoolsite.com postman1
```

### Options

```
      --common-name string   Common name for the certificate. If empty, uses the name.
  -h, --help                 help for CreateSignedCert
      --parent string        Parent cert name to use. Use 'ca' for the toplevel CA. (default "ca")
      --serial string        Serial number for the certificate to create. Should be different for two certificates with the same parent. (default "01")
```

### Options inherited from parent commands

```
      --root string   root directory for all artifacts (default ".")
```

### SEE ALSO

* [vttlstest](../)	 - vttlstest is a tool for generating test certificates, keys, and related artifacts for TLS tests.


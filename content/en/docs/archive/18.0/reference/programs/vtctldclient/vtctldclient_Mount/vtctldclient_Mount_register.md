---
title: Mount register
series: vtctldclient
commit: d3ff5982ddbbb04da1c9ac3c0bff9b09c904c749
---
## vtctldclient Mount register

Register an external Vitess Cluster.

```
vtctldclient Mount register
```

### Examples

```
vtctldclient --server localhost:15999 mount register --name ext1 --topo-type etcd2 --topo-server localhost:12379 --topo-root /vitess/global
```

### Options

```
  -h, --help                 help for register
      --name string          Name to use for the mount.
      --topo-root string     Topo server root path.
      --topo-server string   Topo server address.
      --topo-type string     Topo server implementation to use.
```

### Options inherited from parent commands

```
      --action_timeout duration   timeout to use for the command (default 1h0m0s)
      --compact                   use compact format for otherwise verbose outputs
      --server string             server to use for the connection (required)
```

### SEE ALSO

* [vtctldclient Mount](../)	 - Mount is used to link an external Vitess cluster in order to migrate data from it.


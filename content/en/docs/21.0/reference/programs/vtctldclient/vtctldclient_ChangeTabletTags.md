---
title: ChangeTabletTags
series: vtctldclient
commit: d9bc0da8c46a6f69fec4dd3d50187501d1d6268b
---
## vtctldclient ChangeTabletTags

Changes the tablet tags for the specified tablet, if possible.

### Synopsis

Changes the tablet tags for the specified tablet, if possible.

Tags must be specified as key=value pairs.

```
vtctldclient ChangeTabletTags <alias> <tablet-tag> [ <tablet-tag> ... ]
```

### Options

```
  -h, --help      help for ChangeTabletTags
  -r, --replace   Replace all tablet tags with the tags provided. By default tags are merged/updated.
```

### Options inherited from parent commands

```
      --action_timeout duration              timeout to use for the command (default 1h0m0s)
      --compact                              use compact format for otherwise verbose outputs
      --server string                        server to use for the connection (required)
      --topo-global-root string              the path of the global topology data in the global topology server (default "/vitess/global")
      --topo-global-server-address strings   the address of the global topology server(s) (default [localhost:2379])
      --topo-implementation string           the topology implementation to use (default "etcd2")
```

### SEE ALSO

* [vtctldclient](../)	 - Executes a cluster management command on the remote vtctld server.


---
title: GetPermissions
series: vtctldclient
commit: d9bc0da8c46a6f69fec4dd3d50187501d1d6268b
---
## vtctldclient GetPermissions

Displays the permissions for a tablet.

```
vtctldclient GetPermissions <tablet_alias>
```

### Options

```
  -h, --help   help for GetPermissions
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


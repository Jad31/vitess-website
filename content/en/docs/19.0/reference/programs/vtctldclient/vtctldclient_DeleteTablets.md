---
title: DeleteTablets
series: vtctldclient
commit: 087964bd26b69c5b16c3af9d26515966de9f14bf
---
## vtctldclient DeleteTablets

Deletes tablet(s) from the topology.

```
vtctldclient DeleteTablets <alias> [ <alias> ... ]
```

### Options

```
  -p, --allow-primary   Allow the primary tablet of a shard to be deleted. Use with caution.
  -h, --help            help for DeleteTablets
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


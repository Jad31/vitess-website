---
title: Workflow delete
series: vtctldclient
commit: 6eddcaeac58bed83ebfa3b9ada903ddc8ff36ff6
---
## vtctldclient Workflow delete

Delete a VReplication workflow.

```
vtctldclient Workflow delete
```

### Examples

```
vtctldclient --server localhost:15999 workflow --keyspace customer delete --workflow commerce2customer
```

### Options

```
  -h, --help                 help for delete
      --keep-data            Keep the partially copied table data from the workflow in the target keyspace.
      --keep-routing-rules   Keep the routing rules created for the workflow.
      --shards strings       (Optional) Specifies a comma-separated list of shards to operate on.
  -w, --workflow string      The workflow you want to delete.
```

### Options inherited from parent commands

```
      --action_timeout duration              timeout to use for the command (default 1h0m0s)
      --compact                              use compact format for otherwise verbose outputs
  -k, --keyspace string                      Keyspace context for the workflow.
      --server string                        server to use for the connection (required)
      --topo-global-root string              the path of the global topology data in the global topology server (default "/vitess/global")
      --topo-global-server-address strings   the address of the global topology server(s) (default [localhost:2379])
      --topo-implementation string           the topology implementation to use (default "etcd2")
```

### SEE ALSO

* [vtctldclient Workflow](../)	 - Administer VReplication workflows (Reshard, MoveTables, etc) in the given keyspace.


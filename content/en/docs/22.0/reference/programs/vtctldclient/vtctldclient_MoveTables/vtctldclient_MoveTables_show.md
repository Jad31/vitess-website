---
title: MoveTables show
series: vtctldclient
commit: d9ab9f7a1cf3cae19a1ea06963798a7646e8fb27
---
## vtctldclient MoveTables show

Show the details for a MoveTables VReplication workflow.

```
vtctldclient MoveTables show
```

### Examples

```
vtctldclient --server localhost:15999 MoveTables --workflow commerce2customer --target-keyspace customer show
```

### Options

```
  -h, --help             help for show
      --include-logs     Include recent logs for the workflow. (default true)
      --shards strings   (Optional) Specifies a comma-separated list of shards to operate on.
```

### Options inherited from parent commands

```
      --action_timeout duration              timeout to use for the command (default 1h0m0s)
      --compact                              use compact format for otherwise verbose outputs
      --format string                        The format of the output; supported formats are: text,json. (default "text")
      --server string                        server to use for the connection (required)
      --target-keyspace string               Target keyspace for this workflow.
      --topo-global-root string              the path of the global topology data in the global topology server (default "/vitess/global")
      --topo-global-server-address strings   the address of the global topology server(s) (default [localhost:2379])
      --topo-implementation string           the topology implementation to use (default "etcd2")
  -w, --workflow string                      The workflow you want to perform the command on.
```

### SEE ALSO

* [vtctldclient MoveTables](../)	 - Perform commands related to moving tables from a source keyspace to a target keyspace.


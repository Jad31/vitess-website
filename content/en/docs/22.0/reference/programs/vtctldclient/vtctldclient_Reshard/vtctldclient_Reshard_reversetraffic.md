---
title: Reshard reversetraffic
series: vtctldclient
commit: d9ab9f7a1cf3cae19a1ea06963798a7646e8fb27
---
## vtctldclient Reshard reversetraffic

Reverse traffic for a Reshard VReplication workflow.

```
vtctldclient Reshard reversetraffic
```

### Examples

```
vtctldclient --server localhost:15999 Reshard --workflow cust2cust --target-keyspace customer reversetraffic
```

### Options

```
  -c, --cells strings                          Cells and/or CellAliases to switch traffic in.
      --dry-run                                Print the actions that would be taken and report any known errors that would have occurred.
      --enable-reverse-replication             Setup replication going back to the original source keyspace to support rolling back the traffic cutover. (default true)
      --force                                  Force the traffic switch even if some potentially non-critical actions cannot be performed; for example the tablet refresh fails on some tablets in the keyspace. WARNING: this should be used with extreme caution and only in emergency situations!
  -h, --help                                   help for reversetraffic
      --max-replication-lag-allowed duration   Allow traffic to be switched only if VReplication lag is below this. (default 30s)
      --tablet-types strings                   Tablet types to switch traffic for.
      --timeout duration                       Specifies the maximum time to wait, in seconds, for VReplication to catch up on primary tablets. The traffic switch will be cancelled on timeout. (default 30s)
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

* [vtctldclient Reshard](../)	 - Perform commands related to resharding a keyspace.


---
title: GetBackups
series: vtctldclient
commit: d3ff5982ddbbb04da1c9ac3c0bff9b09c904c749
---
## vtctldclient GetBackups

Lists backups for the given shard.

```
vtctldclient GetBackups [--limit <limit>] [--json] <keyspace/shard>
```

### Options

```
  -h, --help           help for GetBackups
  -j, --json           Output backup info in JSON format rather than a list of backups.
  -l, --limit uint32   Retrieve only the most recent N backups.
```

### Options inherited from parent commands

```
      --action_timeout duration   timeout to use for the command (default 1h0m0s)
      --compact                   use compact format for otherwise verbose outputs
      --server string             server to use for the connection (required)
```

### SEE ALSO

* [vtctldclient](../)	 - Executes a cluster management command on the remote vtctld server.


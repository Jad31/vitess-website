---
title: LookupVindex cancel
series: vtctldclient
commit: d3ff5982ddbbb04da1c9ac3c0bff9b09c904c749
---
## vtctldclient LookupVindex cancel

Cancel the VReplication workflow that backfills the Lookup Vindex.

```
vtctldclient LookupVindex cancel
```

### Examples

```
vtctldclient --server localhost:15999 LookupVindex --name corder_lookup_vdx --table-keyspace customer cancel
```

### Options

```
  -h, --help   help for cancel
```

### Options inherited from parent commands

```
      --action_timeout duration   timeout to use for the command (default 1h0m0s)
      --compact                   use compact format for otherwise verbose outputs
      --name string               The name of the Lookup Vindex to create. This will also be the name of the VReplication workflow created to backfill the Lookup Vindex.
      --server string             server to use for the connection (required)
      --table-keyspace string     The keyspace to create the lookup table in. This is also where the VReplication workflow is created to backfill the Lookup Vindex.
```

### SEE ALSO

* [vtctldclient LookupVindex](../)	 - Perform commands related to creating, backfilling, and externalizing Lookup Vindexes using VReplication workflows.


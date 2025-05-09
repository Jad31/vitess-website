---
title: ApplyVSchema
series: vtctldclient
commit: d9bc0da8c46a6f69fec4dd3d50187501d1d6268b
---
## vtctldclient ApplyVSchema

Applies the VTGate routing schema to the provided keyspace. Shows the result after application.

```
vtctldclient ApplyVSchema {--vschema=<vschema> || --vschema-file=<vschema file> || --sql=<sql> || --sql-file=<sql file>} [--cells=c1,c2,...] [--skip-rebuild] [--dry-run] [--strict] <keyspace>
```

### Options

```
      --cells strings                           Limits the rebuild to the specified cells, after application. Ignored if --skip-rebuild is set.
      --dry-run                                 If set, do not save the altered vschema, simply echo to console.
  -h, --help                                    help for ApplyVSchema
      --skip-rebuild                            Skip rebuilding the SrvSchema objects.
      --sql alter table t add vindex hash(id)   A VSchema DDL SQL statement, e.g. alter table t add vindex hash(id).
      --sql-file string                         Path to a file containing a VSchema DDL SQL.
      --strict                                  If set, treat unknown vindex params as errors.
      --vschema string                          VSchema to apply, in JSON form.
      --vschema-file string                     Path to a file containing the vschema to apply, in JSON form.
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


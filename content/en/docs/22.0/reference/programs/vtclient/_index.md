---
title: vtclient
series: vtclient
commit: d9ab9f7a1cf3cae19a1ea06963798a7646e8fb27
---
## vtclient

vtclient connects to a vtgate server using the standard go driver API.

### Synopsis

vtclient connects to a vtgate server using the standard go driver API.

For query bound variables, we assume place-holders in the query string
in the form of :v1, :v2, etc.

```
vtclient <query> [flags]
```

### Examples

```
vtclient --server vtgate:15991 "SELECT * FROM messages"

vtclient --server vtgate:15991 --target '@primary' --bind_variables '[ 12345, 1, "msg 12345" ]' "INSERT INTO messages (page,time_created_ns,message) VALUES (:v1, :v2, :v3)"
```

### Options

```
      --alsologtostderr                                             log to standard error as well as files
      --bind_variables float                                        bind variables as a json list (default null)
      --config-file string                                          Full path of the config file (with extension) to use. If set, --config-path, --config-type, and --config-name are ignored.
      --config-file-not-found-handling ConfigFileNotFoundHandling   Behavior when a config file is not found. (Options: error, exit, ignore, warn) (default warn)
      --config-name string                                          Name of the config file (without extension) to search for. (default "vtconfig")
      --config-path strings                                         Paths to search for config files in. (default [<WORKDIR>])
      --config-persistence-min-interval duration                    minimum interval between persisting dynamic config changes back to disk (if no change has occurred, nothing is done). (default 1s)
      --config-type string                                          Config file type (omit to infer config type from file extension).
      --count int                                                   DMLs only: Number of times each thread executes the query. Useful for simple, sustained load testing. (default 1)
      --grpc_enable_tracing                                         Enable gRPC tracing.
      --grpc_max_message_size int                                   Maximum allowed RPC message size. Larger messages will be rejected by gRPC with the error 'exceeding the max size'. (default 16777216)
      --grpc_prometheus                                             Enable gRPC monitoring with Prometheus.
  -h, --help                                                        help for vtclient
      --json                                                        Output JSON instead of human-readable table
      --keep_logs duration                                          keep logs for this long (using ctime) (zero to keep forever)
      --keep_logs_by_mtime duration                                 keep logs for this long (using mtime) (zero to keep forever)
      --log_backtrace_at traceLocations                             when logging hits line file:N, emit a stack trace
      --log_dir string                                              If non-empty, write log files in this directory
      --log_err_stacks                                              log stack traces for errors
      --log_rotate_max_size uint                                    size in bytes at which logs are rotated (glog.MaxSize) (default 1887436800)
      --logtostderr                                                 log to standard error instead of files
      --max_sequence_id int                                         max sequence ID.
      --min_sequence_id int                                         min sequence ID to generate. When max_sequence_id > min_sequence_id, for each query, a number is generated in [min_sequence_id, max_sequence_id) and attached to the end of the bind variables.
      --mysql_server_version string                                 MySQL server version to advertise. (default "8.0.30-Vitess")
      --parallel int                                                DMLs only: Number of threads executing the same query in parallel. Useful for simple load testing. (default 1)
      --pprof strings                                               enable profiling
      --pprof-http                                                  enable pprof http endpoints
      --purge_logs_interval duration                                how often try to remove old logs (default 1h0m0s)
      --qps int                                                     queries per second to throttle each thread at.
      --security_policy string                                      the name of a registered security policy to use for controlling access to URLs - empty means allow all for anyone (built-in policies: deny-all, read-only)
      --server string                                               vtgate server to connect to
      --stderrthreshold severityFlag                                logs at or above this threshold go to stderr (default 1)
      --streaming                                                   use a streaming query
      --target string                                               keyspace:shard@tablet_type
      --timeout duration                                            timeout for queries (default 30s)
      --use_random_sequence                                         use random sequence for generating [min_sequence_id, max_sequence_id)
      --v Level                                                     log level for V logs
  -v, --version                                                     print binary version
      --vmodule vModuleFlag                                         comma-separated list of pattern=N settings for file-filtered logging
```


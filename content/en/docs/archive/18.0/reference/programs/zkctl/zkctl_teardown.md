---
title: teardown
series: zkctl
commit: d3ff5982ddbbb04da1c9ac3c0bff9b09c904c749
---
## zkctl teardown

Shuts down the zookeeper server and removes its data dir.

```
zkctl teardown [flags]
```

### Options

```
  -h, --help   help for teardown
```

### Options inherited from parent commands

```
      --alsologtostderr                                             log to standard error as well as files
      --config-file string                                          Full path of the config file (with extension) to use. If set, --config-path, --config-type, and --config-name are ignored.
      --config-file-not-found-handling ConfigFileNotFoundHandling   Behavior when a config file is not found. (Options: error, exit, ignore, warn) (default warn)
      --config-name string                                          Name of the config file (without extension) to search for. (default "vtconfig")
      --config-path strings                                         Paths to search for config files in. (default [<WORKDIR>])
      --config-persistence-min-interval duration                    minimum interval between persisting dynamic config changes back to disk (if no change has occurred, nothing is done). (default 1s)
      --config-type string                                          Config file type (omit to infer config type from file extension).
      --keep_logs duration                                          keep logs for this long (using ctime) (zero to keep forever)
      --keep_logs_by_mtime duration                                 keep logs for this long (using mtime) (zero to keep forever)
      --log_backtrace_at traceLocations                             when logging hits line file:N, emit a stack trace
      --log_dir string                                              If non-empty, write log files in this directory
      --log_err_stacks                                              log stack traces for errors
      --log_rotate_max_size uint                                    size in bytes at which logs are rotated (glog.MaxSize) (default 1887436800)
      --logtostderr                                                 log to standard error instead of files
      --pprof strings                                               enable profiling
      --purge_logs_interval duration                                how often try to remove old logs (default 1h0m0s)
      --stderrthreshold severityFlag                                logs at or above this threshold go to stderr (default 1)
      --v Level                                                     log level for V logs
  -v, --version                                                     print binary version
      --vmodule vModuleFlag                                         comma-separated list of pattern=N settings for file-filtered logging
      --zk.cfg string                                               zkid@server1:leaderPort1:electionPort1:clientPort1,...) (default "6@<hostname>:3801:3802:3803")
      --zk.extra stringArray                                        extra config line(s) to append verbatim to config (flag can be specified more than once)
      --zk.myid uint                                                which server do you want to be? only needed when running multiple instance on one box, otherwise myid is implied by hostname
```

### SEE ALSO

* [zkctl](../)	 - Initializes and controls zookeeper with Vitess-specific configuration.


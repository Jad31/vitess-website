---
title: teardown
series: mysqlctl
commit: d9bc0da8c46a6f69fec4dd3d50187501d1d6268b
---
## mysqlctl teardown

Shuts mysqld down and removes the directory.

### Synopsis

{{< warning >}}
This is a destructive operation.
{{</ warning >}}

Shuts down a `mysqld` instance and removes its data directory.

```
mysqlctl teardown [flags]
```

### Examples

```
mysqlctl --tablet_uid 101 --alsologtostderr teardown
```

### Options

```
  -f, --force                Remove the root directory even if mysqld shutdown fails.
  -h, --help                 help for teardown
      --wait_time duration   How long to wait for mysqld shutdown. (default 5m0s)
```

### Options inherited from parent commands

```
      --alsologtostderr                                             log to standard error as well as files
      --app_idle_timeout duration                                   Idle timeout for app connections (default 1m0s)
      --app_pool_size int                                           Size of the connection pool for app connections (default 40)
      --catch-sigpipe                                               catch and ignore SIGPIPE on stdout and stderr if specified
      --config-file string                                          Full path of the config file (with extension) to use. If set, --config-path, --config-type, and --config-name are ignored.
      --config-file-not-found-handling ConfigFileNotFoundHandling   Behavior when a config file is not found. (Options: error, exit, ignore, warn) (default warn)
      --config-name string                                          Name of the config file (without extension) to search for. (default "vtconfig")
      --config-path strings                                         Paths to search for config files in. (default [<WORKDIR>])
      --config-persistence-min-interval duration                    minimum interval between persisting dynamic config changes back to disk (if no change has occurred, nothing is done). (default 1s)
      --config-type string                                          Config file type (omit to infer config type from file extension).
      --db-credentials-file string                                  db credentials file; send SIGHUP to reload this file
      --db-credentials-server string                                db credentials server type ('file' - file implementation; 'vault' - HashiCorp Vault implementation) (default "file")
      --db-credentials-vault-addr string                            URL to Vault server
      --db-credentials-vault-path string                            Vault path to credentials JSON blob, e.g.: secret/data/prod/dbcreds
      --db-credentials-vault-role-mountpoint string                 Vault AppRole mountpoint; can also be passed using VAULT_MOUNTPOINT environment variable (default "approle")
      --db-credentials-vault-role-secretidfile string               Path to file containing Vault AppRole secret_id; can also be passed using VAULT_SECRETID environment variable
      --db-credentials-vault-roleid string                          Vault AppRole id; can also be passed using VAULT_ROLEID environment variable
      --db-credentials-vault-timeout duration                       Timeout for vault API operations (default 10s)
      --db-credentials-vault-tls-ca string                          Path to CA PEM for validating Vault server certificate
      --db-credentials-vault-tokenfile string                       Path to file containing Vault auth token; token can also be passed using VAULT_TOKEN environment variable
      --db-credentials-vault-ttl duration                           How long to cache DB credentials from the Vault server (default 30m0s)
      --db_charset string                                           Character set/collation used for this tablet. Make sure to configure this to a charset/collation supported by the lowest MySQL version in your environment. (default "utf8mb4")
      --db_conn_query_info                                          enable parsing and processing of QUERY_OK info fields
      --db_connect_timeout_ms int                                   connection timeout to mysqld in milliseconds (0 for no timeout)
      --db_dba_password string                                      db dba password
      --db_dba_use_ssl                                              Set this flag to false to make the dba connection to not use ssl (default true)
      --db_dba_user string                                          db dba user userKey (default "vt_dba")
      --db_flags uint                                               Flag values as defined by MySQL.
      --db_flavor string                                            Flavor overrid. Valid value is FilePos.
      --db_host string                                              The host name for the tcp connection.
      --db_port int                                                 tcp port
      --db_server_name string                                       server name of the DB we are connecting to.
      --db_socket string                                            The unix socket to connect on. If this is specified, host and port will not be used.
      --db_ssl_ca string                                            connection ssl ca
      --db_ssl_ca_path string                                       connection ssl ca path
      --db_ssl_cert string                                          connection ssl certificate
      --db_ssl_key string                                           connection ssl key
      --db_ssl_mode SslMode                                         SSL mode to connect with. One of disabled, preferred, required, verify_ca & verify_identity.
      --db_tls_min_version string                                   Configures the minimal TLS version negotiated when SSL is enabled. Defaults to TLSv1.2. Options: TLSv1.0, TLSv1.1, TLSv1.2, TLSv1.3.
      --dba_idle_timeout duration                                   Idle timeout for dba connections (default 1m0s)
      --dba_pool_size int                                           Size of the connection pool for dba connections (default 20)
      --keep_logs duration                                          keep logs for this long (using ctime) (zero to keep forever)
      --keep_logs_by_mtime duration                                 keep logs for this long (using mtime) (zero to keep forever)
      --lameduck-period duration                                    keep running at least this long after SIGTERM before stopping (default 50ms)
      --log_backtrace_at traceLocations                             when logging hits line file:N, emit a stack trace
      --log_dir string                                              If non-empty, write log files in this directory
      --log_err_stacks                                              log stack traces for errors
      --log_rotate_max_size uint                                    size in bytes at which logs are rotated (glog.MaxSize) (default 1887436800)
      --logtostderr                                                 log to standard error instead of files
      --max-stack-size int                                          configure the maximum stack size in bytes (default 67108864)
      --mysql_port int                                              MySQL port. (default 3306)
      --mysql_server_version string                                 MySQL server version to advertise. (default "8.0.30-Vitess")
      --mysql_socket string                                         Path to the mysqld socket file.
      --mysqlctl_client_protocol string                             the protocol to use to talk to the mysqlctl server (default "grpc")
      --mysqlctl_mycnf_template string                              template file to use for generating the my.cnf file during server init
      --mysqlctl_socket string                                      socket file to use for remote mysqlctl actions (empty for local actions)
      --onclose_timeout duration                                    wait no more than this for OnClose handlers before stopping (default 10s)
      --onterm_timeout duration                                     wait no more than this for OnTermSync handlers before stopping (default 10s)
      --pid_file string                                             If set, the process will write its pid to the named file, and delete it on graceful shutdown.
      --pool_hostname_resolve_interval duration                     if set force an update to all hostnames and reconnect if changed, defaults to 0 (disabled)
      --pprof strings                                               enable profiling
      --pprof-http                                                  enable pprof http endpoints
      --purge_logs_interval duration                                how often try to remove old logs (default 1h0m0s)
      --replication_connect_retry duration                          how long to wait in between replica reconnect attempts. Only precise to the second. (default 10s)
      --security_policy string                                      the name of a registered security policy to use for controlling access to URLs - empty means allow all for anyone (built-in policies: deny-all, read-only)
      --service_map strings                                         comma separated list of services to enable (or disable if prefixed with '-') Example: grpc-queryservice
      --socket_file string                                          Local unix socket file to listen on
      --stderrthreshold severityFlag                                logs at or above this threshold go to stderr (default 1)
      --table-refresh-interval int                                  interval in milliseconds to refresh tables in status page with refreshRequired class
      --tablet_dir string                                           The directory within the vtdataroot to store vttablet/mysql files. Defaults to being generated by the tablet uid.
      --tablet_uid uint32                                           Tablet UID. (default 41983)
      --v Level                                                     log level for V logs
  -v, --version                                                     print binary version
      --vmodule vModuleFlag                                         comma-separated list of pattern=N settings for file-filtered logging
```

### SEE ALSO

* [mysqlctl](../)	 - mysqlctl initializes and controls mysqld with Vitess-specific configuration.


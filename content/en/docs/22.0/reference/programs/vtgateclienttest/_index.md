---
title: vtgateclienttest
series: vtgateclienttest
commit: d9ab9f7a1cf3cae19a1ea06963798a7646e8fb27
---
## vtgateclienttest

vtgateclienttest is a chain of vtgateservice.VTGateService implementations, each one being responsible for one test scenario.

```
vtgateclienttest [flags]
```

### Options

```
      --alsologtostderr                                                  log to standard error as well as files
      --bind-address string                                              Bind address for the server. If empty, the server will listen on all available unicast and anycast IP addresses of the local system.
      --catch-sigpipe                                                    catch and ignore SIGPIPE on stdout and stderr if specified
      --config-file string                                               Full path of the config file (with extension) to use. If set, --config-path, --config-type, and --config-name are ignored.
      --config-file-not-found-handling ConfigFileNotFoundHandling        Behavior when a config file is not found. (Options: error, exit, ignore, warn) (default warn)
      --config-name string                                               Name of the config file (without extension) to search for. (default "vtconfig")
      --config-path strings                                              Paths to search for config files in. (default [<WORKDIR>])
      --config-persistence-min-interval duration                         minimum interval between persisting dynamic config changes back to disk (if no change has occurred, nothing is done). (default 1s)
      --config-type string                                               Config file type (omit to infer config type from file extension).
      --default_tablet_type topodatapb.TabletType                        The default tablet type to set for queries, when one is not explicitly selected. (default PRIMARY)
      --grpc-dial-concurrency-limit int                                  Maximum concurrency of grpc dial operations. This should be less than the golang max thread limit of 10000. (default 1024)
      --grpc_auth_mode string                                            Which auth plugin implementation to use (eg: static)
      --grpc_auth_mtls_allowed_substrings string                         List of substrings of at least one of the client certificate names (separated by colon).
      --grpc_auth_static_client_creds string                             When using grpc_static_auth in the server, this file provides the credentials to use to authenticate with server.
      --grpc_auth_static_password_file string                            JSON File to read the users/passwords from.
      --grpc_bind_address string                                         Bind address for gRPC calls. If empty, listen on all addresses.
      --grpc_ca string                                                   server CA to use for gRPC connections, requires TLS, and enforces client certificate check
      --grpc_cert string                                                 server certificate to use for gRPC connections, requires grpc_key, enables TLS
      --grpc_compression string                                          Which protocol to use for compressing gRPC. Default: nothing. Supported: snappy
      --grpc_crl string                                                  path to a certificate revocation list in PEM format, client certificates will be further verified against this file during TLS handshake
      --grpc_enable_optional_tls                                         enable optional TLS mode when a server accepts both TLS and plain-text connections on the same port
      --grpc_enable_tracing                                              Enable gRPC tracing.
      --grpc_initial_conn_window_size int                                gRPC initial connection window size
      --grpc_initial_window_size int                                     gRPC initial window size
      --grpc_keepalive_time duration                                     After a duration of this time, if the client doesn't see any activity, it pings the server to see if the transport is still alive. (default 10s)
      --grpc_keepalive_timeout duration                                  After having pinged for keepalive check, the client waits for a duration of Timeout and if no activity is seen even after that the connection is closed. (default 10s)
      --grpc_key string                                                  server private key to use for gRPC connections, requires grpc_cert, enables TLS
      --grpc_max_connection_age duration                                 Maximum age of a client connection before GoAway is sent. (default 2562047h47m16.854775807s)
      --grpc_max_connection_age_grace duration                           Additional grace period after grpc_max_connection_age, after which connections are forcibly closed. (default 2562047h47m16.854775807s)
      --grpc_max_message_size int                                        Maximum allowed RPC message size. Larger messages will be rejected by gRPC with the error 'exceeding the max size'. (default 16777216)
      --grpc_port int                                                    Port to listen on for gRPC calls. If zero, do not listen.
      --grpc_prometheus                                                  Enable gRPC monitoring with Prometheus.
      --grpc_server_ca string                                            path to server CA in PEM format, which will be combine with server cert, return full certificate chain to clients
      --grpc_server_initial_conn_window_size int                         gRPC server initial connection window size
      --grpc_server_initial_window_size int                              gRPC server initial window size
      --grpc_server_keepalive_enforcement_policy_min_time duration       gRPC server minimum keepalive time (default 10s)
      --grpc_server_keepalive_enforcement_policy_permit_without_stream   gRPC server permit client keepalive pings even when there are no active streams (RPCs)
      --grpc_server_keepalive_time duration                              After a duration of this time, if the server doesn't see any activity, it pings the client to see if the transport is still alive. (default 10s)
      --grpc_server_keepalive_timeout duration                           After having pinged for keepalive check, the server waits for a duration of Timeout and if no activity is seen even after that the connection is closed. (default 10s)
  -h, --help                                                             help for vtgateclienttest
      --keep_logs duration                                               keep logs for this long (using ctime) (zero to keep forever)
      --keep_logs_by_mtime duration                                      keep logs for this long (using mtime) (zero to keep forever)
      --lameduck-period duration                                         keep running at least this long after SIGTERM before stopping (default 50ms)
      --log_backtrace_at traceLocations                                  when logging hits line file:N, emit a stack trace
      --log_dir string                                                   If non-empty, write log files in this directory
      --log_err_stacks                                                   log stack traces for errors
      --log_rotate_max_size uint                                         size in bytes at which logs are rotated (glog.MaxSize) (default 1887436800)
      --logtostderr                                                      log to standard error instead of files
      --max-stack-size int                                               configure the maximum stack size in bytes (default 67108864)
      --mysql_server_version string                                      MySQL server version to advertise. (default "8.0.30-Vitess")
      --onclose_timeout duration                                         wait no more than this for OnClose handlers before stopping (default 10s)
      --onterm_timeout duration                                          wait no more than this for OnTermSync handlers before stopping (default 10s)
      --pid_file string                                                  If set, the process will write its pid to the named file, and delete it on graceful shutdown.
      --port int                                                         port for the server
      --pprof strings                                                    enable profiling
      --pprof-http                                                       enable pprof http endpoints
      --purge_logs_interval duration                                     how often try to remove old logs (default 1h0m0s)
      --security_policy string                                           the name of a registered security policy to use for controlling access to URLs - empty means allow all for anyone (built-in policies: deny-all, read-only)
      --service_map strings                                              comma separated list of services to enable (or disable if prefixed with '-') Example: grpc-queryservice
      --stderrthreshold severityFlag                                     logs at or above this threshold go to stderr (default 1)
      --table-refresh-interval int                                       interval in milliseconds to refresh tables in status page with refreshRequired class
      --v Level                                                          log level for V logs
  -v, --version                                                          print binary version
      --vmodule vModuleFlag                                              comma-separated list of pattern=N settings for file-filtered logging
      --vschema_ddl_authorized_users string                              List of users authorized to execute vschema ddl operations, or '%' to allow all users.
```


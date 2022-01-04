[Node.js](https://nodejs.org/ "Go back to the home page")

-   [About this
    documentation](https://nodejs.org/api/documentation.html)
-   [Usage and example](https://nodejs.org/api/synopsis.html)

* * * * *

-   [Assertion testing](https://nodejs.org/api/assert.html)
-   [Async hooks](https://nodejs.org/api/async_hooks.html)
-   [Buffer](https://nodejs.org/api/buffer.html)
-   [C++ addons](https://nodejs.org/api/addons.html)
-   [C/C++ addons with N-API](https://nodejs.org/api/n-api.html)
-   [C++ embedder API](https://nodejs.org/api/embedding.html)
-   [Child processes](https://nodejs.org/api/child_process.html)
-   [Cluster](https://nodejs.org/api/cluster.html)
-   [Command line options](https://nodejs.org/api/cli.html)
-   [Console](https://nodejs.org/api/console.html)
-   [Crypto](https://nodejs.org/api/crypto.html)
-   [Debugger](https://nodejs.org/api/debugger.html)
-   [Deprecated APIs](https://nodejs.org/api/deprecations.html)
-   [DNS](https://nodejs.org/api/dns.html)
-   [Domain](https://nodejs.org/api/domain.html)
-   [Errors](https://nodejs.org/api/errors.html)
-   [Events](https://nodejs.org/api/events.html)
-   [File system](https://nodejs.org/api/fs.html)
-   [Globals](https://nodejs.org/api/globals.html)
-   [HTTP](https://nodejs.org/api/http.html)
-   [HTTP/2](https://nodejs.org/api/http2.html)
-   [HTTPS](https://nodejs.org/api/https.html)
-   [Inspector](https://nodejs.org/api/inspector.html)
-   [Internationalization](https://nodejs.org/api/intl.html)
-   [Modules: CommonJS modules](https://nodejs.org/api/modules.html)
-   [Modules: ECMAScript modules](https://nodejs.org/api/esm.html)
-   [Modules: `module` API](https://nodejs.org/api/module.html)
-   [Net](https://nodejs.org/api/net.html)
-   [OS](https://nodejs.org/api/os.html)
-   [Path](https://nodejs.org/api/path.html)
-   [Performance hooks](https://nodejs.org/api/perf_hooks.html)
-   [Policies](https://nodejs.org/api/policy.html)
-   [Process](https://nodejs.org/api/process.html)
-   [Punycode](https://nodejs.org/api/punycode.html)
-   [Query strings](https://nodejs.org/api/querystring.html)
-   [Readline](https://nodejs.org/api/readline.html)
-   [REPL](https://nodejs.org/api/repl.html)
-   [Report](https://nodejs.org/api/report.html)
-   [Stream](https://nodejs.org/api/stream.html)
-   [String decoder](https://nodejs.org/api/string_decoder.html)
-   [Timers](https://nodejs.org/api/timers.html)
-   [TLS/SSL](https://nodejs.org/api/tls.html)
-   [Trace events](https://nodejs.org/api/tracing.html)
-   [TTY](https://nodejs.org/api/tty.html)
-   [UDP/datagram](https://nodejs.org/api/dgram.html)
-   [URL](https://nodejs.org/api/url.html)
-   [Utilities](https://nodejs.org/api/util.html)
-   [V8](https://nodejs.org/api/v8.html)
-   [VM](https://nodejs.org/api/vm.html)
-   [WASI](https://nodejs.org/api/wasi.html)
-   [Worker threads](https://nodejs.org/api/worker_threads.html)
-   [Zlib](https://nodejs.org/api/zlib.html)

* * * * *

-   [Code repository and issue tracker](https://github.com/nodejs/node)

Node.js v14.10.1 Documentation
==============================

-   [Index](https://nodejs.org/api/index.html)
-   [View on single page](https://nodejs.org/api/all.html)
-   [View as JSON](https://nodejs.org/api/errors.json)
-   [View another version ▼](https://nodejs.org/api/errors.html#)
    1.  [14.x](https://nodejs.org/docs/latest-v14.x/api/errors.html)
    2.  [13.x](https://nodejs.org/docs/latest-v13.x/api/errors.html)
    3.  [12.x
        **LTS**](https://nodejs.org/docs/latest-v12.x/api/errors.html)
    4.  [11.x](https://nodejs.org/docs/latest-v11.x/api/errors.html)
    5.  [10.x
        **LTS**](https://nodejs.org/docs/latest-v10.x/api/errors.html)
    6.  [9.x](https://nodejs.org/docs/latest-v9.x/api/errors.html)
    7.  [8.x](https://nodejs.org/docs/latest-v8.x/api/errors.html)
    8.  [7.x](https://nodejs.org/docs/latest-v7.x/api/errors.html)
    9.  [6.x](https://nodejs.org/docs/latest-v6.x/api/errors.html)
    10. [5.x](https://nodejs.org/docs/latest-v5.x/api/errors.html)
    11. [4.x](https://nodejs.org/docs/latest-v4.x/api/errors.html)
-   [](https://github.com/nodejs/node/edit/master/doc/api/errors.md)
    Edit on GitHub

* * * * *

Table of Contents
-----------------

-   [Errors](https://nodejs.org/api/errors.html#errors_errors)

    -   [Error propagation and
        interception](https://nodejs.org/api/errors.html#errors_error_propagation_and_interception)

        -   [Error-first
            callbacks](https://nodejs.org/api/errors.html#errors_error_first_callbacks)
    -   [Class:
        `Error`](https://nodejs.org/api/errors.html#errors_class_error)

        -   [`new Error(message)`](https://nodejs.org/api/errors.html#errors_new_error_message)
        -   [`Error.captureStackTrace(targetObject[, constructorOpt])`](https://nodejs.org/api/errors.html#errors_error_capturestacktrace_targetobject_constructoropt)
        -   [`Error.stackTraceLimit`](https://nodejs.org/api/errors.html#errors_error_stacktracelimit)
        -   [`error.code`](https://nodejs.org/api/errors.html#errors_error_code)
        -   [`error.message`](https://nodejs.org/api/errors.html#errors_error_message)
        -   [`error.stack`](https://nodejs.org/api/errors.html#errors_error_stack)
    -   [Class:
        `AssertionError`](https://nodejs.org/api/errors.html#errors_class_assertionerror)
    -   [Class:
        `RangeError`](https://nodejs.org/api/errors.html#errors_class_rangeerror)
    -   [Class:
        `ReferenceError`](https://nodejs.org/api/errors.html#errors_class_referenceerror)
    -   [Class:
        `SyntaxError`](https://nodejs.org/api/errors.html#errors_class_syntaxerror)
    -   [Class:
        `SystemError`](https://nodejs.org/api/errors.html#errors_class_systemerror)

        -   [`error.address`](https://nodejs.org/api/errors.html#errors_error_address)
        -   [`error.code`](https://nodejs.org/api/errors.html#errors_error_code_1)
        -   [`error.dest`](https://nodejs.org/api/errors.html#errors_error_dest)
        -   [`error.errno`](https://nodejs.org/api/errors.html#errors_error_errno)
        -   [`error.info`](https://nodejs.org/api/errors.html#errors_error_info)
        -   [`error.message`](https://nodejs.org/api/errors.html#errors_error_message_1)
        -   [`error.path`](https://nodejs.org/api/errors.html#errors_error_path)
        -   [`error.port`](https://nodejs.org/api/errors.html#errors_error_port)
        -   [`error.syscall`](https://nodejs.org/api/errors.html#errors_error_syscall)
        -   [Common system
            errors](https://nodejs.org/api/errors.html#errors_common_system_errors)
    -   [Class:
        `TypeError`](https://nodejs.org/api/errors.html#errors_class_typeerror)
    -   [Exceptions vs.
        errors](https://nodejs.org/api/errors.html#errors_exceptions_vs_errors)
    -   [OpenSSL
        errors](https://nodejs.org/api/errors.html#errors_openssl_errors)

        -   [`error.opensslErrorStack`](https://nodejs.org/api/errors.html#errors_error_opensslerrorstack)
        -   [`error.function`](https://nodejs.org/api/errors.html#errors_error_function)
        -   [`error.library`](https://nodejs.org/api/errors.html#errors_error_library)
        -   [`error.reason`](https://nodejs.org/api/errors.html#errors_error_reason)
    -   [Node.js error
        codes](https://nodejs.org/api/errors.html#errors_node_js_error_codes)

        -   [`ERR_AMBIGUOUS_ARGUMENT`](https://nodejs.org/api/errors.html#errors_err_ambiguous_argument)
        -   [`ERR_ARG_NOT_ITERABLE`](https://nodejs.org/api/errors.html#errors_err_arg_not_iterable)
        -   [`ERR_ASSERTION`](https://nodejs.org/api/errors.html#errors_err_assertion)
        -   [`ERR_ASYNC_CALLBACK`](https://nodejs.org/api/errors.html#errors_err_async_callback)
        -   [`ERR_ASYNC_TYPE`](https://nodejs.org/api/errors.html#errors_err_async_type)
        -   [`ERR_BROTLI_COMPRESSION_FAILED`](https://nodejs.org/api/errors.html#errors_err_brotli_compression_failed)
        -   [`ERR_BROTLI_INVALID_PARAM`](https://nodejs.org/api/errors.html#errors_err_brotli_invalid_param)
        -   [`ERR_BUFFER_CONTEXT_NOT_AVAILABLE`](https://nodejs.org/api/errors.html#errors_err_buffer_context_not_available)
        -   [`ERR_BUFFER_OUT_OF_BOUNDS`](https://nodejs.org/api/errors.html#errors_err_buffer_out_of_bounds)
        -   [`ERR_BUFFER_TOO_LARGE`](https://nodejs.org/api/errors.html#errors_err_buffer_too_large)
        -   [`ERR_CANNOT_WATCH_SIGINT`](https://nodejs.org/api/errors.html#errors_err_cannot_watch_sigint)
        -   [`ERR_CHILD_CLOSED_BEFORE_REPLY`](https://nodejs.org/api/errors.html#errors_err_child_closed_before_reply)
        -   [`ERR_CHILD_PROCESS_IPC_REQUIRED`](https://nodejs.org/api/errors.html#errors_err_child_process_ipc_required)
        -   [`ERR_CHILD_PROCESS_STDIO_MAXBUFFER`](https://nodejs.org/api/errors.html#errors_err_child_process_stdio_maxbuffer)
        -   [`ERR_CONSOLE_WRITABLE_STREAM`](https://nodejs.org/api/errors.html#errors_err_console_writable_stream)
        -   [`ERR_CONTEXT_NOT_INITIALIZED`](https://nodejs.org/api/errors.html#errors_err_context_not_initialized)
        -   [`ERR_CONSTRUCT_CALL_REQUIRED`](https://nodejs.org/api/errors.html#errors_err_construct_call_required)
        -   [`ERR_CONSTRUCT_CALL_INVALID`](https://nodejs.org/api/errors.html#errors_err_construct_call_invalid)
        -   [`ERR_CPU_USAGE`](https://nodejs.org/api/errors.html#errors_err_cpu_usage)
        -   [`ERR_CRYPTO_CUSTOM_ENGINE_NOT_SUPPORTED`](https://nodejs.org/api/errors.html#errors_err_crypto_custom_engine_not_supported)
        -   [`ERR_CRYPTO_ECDH_INVALID_FORMAT`](https://nodejs.org/api/errors.html#errors_err_crypto_ecdh_invalid_format)
        -   [`ERR_CRYPTO_ECDH_INVALID_PUBLIC_KEY`](https://nodejs.org/api/errors.html#errors_err_crypto_ecdh_invalid_public_key)
        -   [`ERR_CRYPTO_ENGINE_UNKNOWN`](https://nodejs.org/api/errors.html#errors_err_crypto_engine_unknown)
        -   [`ERR_CRYPTO_FIPS_FORCED`](https://nodejs.org/api/errors.html#errors_err_crypto_fips_forced)
        -   [`ERR_CRYPTO_FIPS_UNAVAILABLE`](https://nodejs.org/api/errors.html#errors_err_crypto_fips_unavailable)
        -   [`ERR_CRYPTO_HASH_FINALIZED`](https://nodejs.org/api/errors.html#errors_err_crypto_hash_finalized)
        -   [`ERR_CRYPTO_HASH_UPDATE_FAILED`](https://nodejs.org/api/errors.html#errors_err_crypto_hash_update_failed)
        -   [`ERR_CRYPTO_INCOMPATIBLE_KEY`](https://nodejs.org/api/errors.html#errors_err_crypto_incompatible_key)
        -   [`ERR_CRYPTO_INCOMPATIBLE_KEY_OPTIONS`](https://nodejs.org/api/errors.html#errors_err_crypto_incompatible_key_options)
        -   [`ERR_CRYPTO_INVALID_DIGEST`](https://nodejs.org/api/errors.html#errors_err_crypto_invalid_digest)
        -   [`ERR_CRYPTO_INVALID_KEY_OBJECT_TYPE`](https://nodejs.org/api/errors.html#errors_err_crypto_invalid_key_object_type)
        -   [`ERR_CRYPTO_INVALID_STATE`](https://nodejs.org/api/errors.html#errors_err_crypto_invalid_state)
        -   [`ERR_CRYPTO_PBKDF2_ERROR`](https://nodejs.org/api/errors.html#errors_err_crypto_pbkdf2_error)
        -   [`ERR_CRYPTO_SCRYPT_INVALID_PARAMETER`](https://nodejs.org/api/errors.html#errors_err_crypto_scrypt_invalid_parameter)
        -   [`ERR_CRYPTO_SCRYPT_NOT_SUPPORTED`](https://nodejs.org/api/errors.html#errors_err_crypto_scrypt_not_supported)
        -   [`ERR_CRYPTO_SIGN_KEY_REQUIRED`](https://nodejs.org/api/errors.html#errors_err_crypto_sign_key_required)
        -   [`ERR_CRYPTO_TIMING_SAFE_EQUAL_LENGTH`](https://nodejs.org/api/errors.html#errors_err_crypto_timing_safe_equal_length)
        -   [`ERR_CRYPTO_UNKNOWN_CIPHER`](https://nodejs.org/api/errors.html#errors_err_crypto_unknown_cipher)
        -   [`ERR_CRYPTO_UNKNOWN_DH_GROUP`](https://nodejs.org/api/errors.html#errors_err_crypto_unknown_dh_group)
        -   [`ERR_DIR_CLOSED`](https://nodejs.org/api/errors.html#errors_err_dir_closed)
        -   [`ERR_DIR_CONCURRENT_OPERATION`](https://nodejs.org/api/errors.html#errors_err_dir_concurrent_operation)
        -   [`ERR_DNS_SET_SERVERS_FAILED`](https://nodejs.org/api/errors.html#errors_err_dns_set_servers_failed)
        -   [`ERR_DOMAIN_CALLBACK_NOT_AVAILABLE`](https://nodejs.org/api/errors.html#errors_err_domain_callback_not_available)
        -   [`ERR_DOMAIN_CANNOT_SET_UNCAUGHT_EXCEPTION_CAPTURE`](https://nodejs.org/api/errors.html#errors_err_domain_cannot_set_uncaught_exception_capture)
        -   [`ERR_ENCODING_INVALID_ENCODED_DATA`](https://nodejs.org/api/errors.html#errors_err_encoding_invalid_encoded_data)
        -   [`ERR_ENCODING_NOT_SUPPORTED`](https://nodejs.org/api/errors.html#errors_err_encoding_not_supported)
        -   [`ERR_EVAL_ESM_CANNOT_PRINT`](https://nodejs.org/api/errors.html#errors_err_eval_esm_cannot_print)
        -   [`ERR_EVENT_RECURSION`](https://nodejs.org/api/errors.html#errors_err_event_recursion)
        -   [`ERR_EXECUTION_ENVIRONMENT_NOT_AVAILABLE`](https://nodejs.org/api/errors.html#errors_err_execution_environment_not_available)
        -   [`ERR_FALSY_VALUE_REJECTION`](https://nodejs.org/api/errors.html#errors_err_falsy_value_rejection)

            -   [`ERR_FEATURE_UNAVAILABLE_ON_PLATFORM`](https://nodejs.org/api/errors.html#errors_err_feature_unavailable_on_platform)
        -   [`ERR_FS_FILE_TOO_LARGE`](https://nodejs.org/api/errors.html#errors_err_fs_file_too_large)
        -   [`ERR_FS_INVALID_SYMLINK_TYPE`](https://nodejs.org/api/errors.html#errors_err_fs_invalid_symlink_type)
        -   [`ERR_HTTP_HEADERS_SENT`](https://nodejs.org/api/errors.html#errors_err_http_headers_sent)
        -   [`ERR_HTTP_INVALID_HEADER_VALUE`](https://nodejs.org/api/errors.html#errors_err_http_invalid_header_value)
        -   [`ERR_HTTP_INVALID_STATUS_CODE`](https://nodejs.org/api/errors.html#errors_err_http_invalid_status_code)
        -   [`ERR_HTTP_TRAILER_INVALID`](https://nodejs.org/api/errors.html#errors_err_http_trailer_invalid)
        -   [`ERR_HTTP2_ALTSVC_INVALID_ORIGIN`](https://nodejs.org/api/errors.html#errors_err_http2_altsvc_invalid_origin)
        -   [`ERR_HTTP2_ALTSVC_LENGTH`](https://nodejs.org/api/errors.html#errors_err_http2_altsvc_length)
        -   [`ERR_HTTP2_CONNECT_AUTHORITY`](https://nodejs.org/api/errors.html#errors_err_http2_connect_authority)
        -   [`ERR_HTTP2_CONNECT_PATH`](https://nodejs.org/api/errors.html#errors_err_http2_connect_path)
        -   [`ERR_HTTP2_CONNECT_SCHEME`](https://nodejs.org/api/errors.html#errors_err_http2_connect_scheme)
        -   [`ERR_HTTP2_ERROR`](https://nodejs.org/api/errors.html#errors_err_http2_error)
        -   [`ERR_HTTP2_GOAWAY_SESSION`](https://nodejs.org/api/errors.html#errors_err_http2_goaway_session)
        -   [`ERR_HTTP2_HEADERS_AFTER_RESPOND`](https://nodejs.org/api/errors.html#errors_err_http2_headers_after_respond)
        -   [`ERR_HTTP2_HEADERS_SENT`](https://nodejs.org/api/errors.html#errors_err_http2_headers_sent)
        -   [`ERR_HTTP2_HEADER_SINGLE_VALUE`](https://nodejs.org/api/errors.html#errors_err_http2_header_single_value)
        -   [`ERR_HTTP2_INFO_STATUS_NOT_ALLOWED`](https://nodejs.org/api/errors.html#errors_err_http2_info_status_not_allowed)
        -   [`ERR_HTTP2_INVALID_CONNECTION_HEADERS`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_connection_headers)
        -   [`ERR_HTTP2_INVALID_HEADER_VALUE`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_header_value)
        -   [`ERR_HTTP2_INVALID_INFO_STATUS`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_info_status)
        -   [`ERR_HTTP2_INVALID_ORIGIN`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_origin)
        -   [`ERR_HTTP2_INVALID_PACKED_SETTINGS_LENGTH`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_packed_settings_length)
        -   [`ERR_HTTP2_INVALID_PSEUDOHEADER`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_pseudoheader)
        -   [`ERR_HTTP2_INVALID_SESSION`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_session)
        -   [`ERR_HTTP2_INVALID_SETTING_VALUE`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_setting_value)
        -   [`ERR_HTTP2_INVALID_STREAM`](https://nodejs.org/api/errors.html#errors_err_http2_invalid_stream)
        -   [`ERR_HTTP2_MAX_PENDING_SETTINGS_ACK`](https://nodejs.org/api/errors.html#errors_err_http2_max_pending_settings_ack)
        -   [`ERR_HTTP2_NESTED_PUSH`](https://nodejs.org/api/errors.html#errors_err_http2_nested_push)
        -   [`ERR_HTTP2_NO_SOCKET_MANIPULATION`](https://nodejs.org/api/errors.html#errors_err_http2_no_socket_manipulation)
        -   [`ERR_HTTP2_ORIGIN_LENGTH`](https://nodejs.org/api/errors.html#errors_err_http2_origin_length)
        -   [`ERR_HTTP2_OUT_OF_STREAMS`](https://nodejs.org/api/errors.html#errors_err_http2_out_of_streams)
        -   [`ERR_HTTP2_PAYLOAD_FORBIDDEN`](https://nodejs.org/api/errors.html#errors_err_http2_payload_forbidden)
        -   [`ERR_HTTP2_PING_CANCEL`](https://nodejs.org/api/errors.html#errors_err_http2_ping_cancel)
        -   [`ERR_HTTP2_PING_LENGTH`](https://nodejs.org/api/errors.html#errors_err_http2_ping_length)
        -   [`ERR_HTTP2_PSEUDOHEADER_NOT_ALLOWED`](https://nodejs.org/api/errors.html#errors_err_http2_pseudoheader_not_allowed)
        -   [`ERR_HTTP2_PUSH_DISABLED`](https://nodejs.org/api/errors.html#errors_err_http2_push_disabled)
        -   [`ERR_HTTP2_SEND_FILE`](https://nodejs.org/api/errors.html#errors_err_http2_send_file)
        -   [`ERR_HTTP2_SEND_FILE_NOSEEK`](https://nodejs.org/api/errors.html#errors_err_http2_send_file_noseek)
        -   [`ERR_HTTP2_SESSION_ERROR`](https://nodejs.org/api/errors.html#errors_err_http2_session_error)
        -   [`ERR_HTTP2_SETTINGS_CANCEL`](https://nodejs.org/api/errors.html#errors_err_http2_settings_cancel)
        -   [`ERR_HTTP2_SOCKET_BOUND`](https://nodejs.org/api/errors.html#errors_err_http2_socket_bound)
        -   [`ERR_HTTP2_SOCKET_UNBOUND`](https://nodejs.org/api/errors.html#errors_err_http2_socket_unbound)
        -   [`ERR_HTTP2_STATUS_101`](https://nodejs.org/api/errors.html#errors_err_http2_status_101)
        -   [`ERR_HTTP2_STATUS_INVALID`](https://nodejs.org/api/errors.html#errors_err_http2_status_invalid)
        -   [`ERR_HTTP2_STREAM_CANCEL`](https://nodejs.org/api/errors.html#errors_err_http2_stream_cancel)
        -   [`ERR_HTTP2_STREAM_ERROR`](https://nodejs.org/api/errors.html#errors_err_http2_stream_error)
        -   [`ERR_HTTP2_STREAM_SELF_DEPENDENCY`](https://nodejs.org/api/errors.html#errors_err_http2_stream_self_dependency)
        -   [`ERR_HTTP2_TRAILERS_ALREADY_SENT`](https://nodejs.org/api/errors.html#errors_err_http2_trailers_already_sent)
        -   [`ERR_HTTP2_TRAILERS_NOT_READY`](https://nodejs.org/api/errors.html#errors_err_http2_trailers_not_ready)
        -   [`ERR_HTTP2_UNSUPPORTED_PROTOCOL`](https://nodejs.org/api/errors.html#errors_err_http2_unsupported_protocol)
        -   [`ERR_INTERNAL_ASSERTION`](https://nodejs.org/api/errors.html#errors_err_internal_assertion)
        -   [`ERR_INCOMPATIBLE_OPTION_PAIR`](https://nodejs.org/api/errors.html#errors_err_incompatible_option_pair)
        -   [`ERR_INPUT_TYPE_NOT_ALLOWED`](https://nodejs.org/api/errors.html#errors_err_input_type_not_allowed)
        -   [`ERR_INSPECTOR_ALREADY_ACTIVATED`](https://nodejs.org/api/errors.html#errors_err_inspector_already_activated)
        -   [`ERR_INSPECTOR_ALREADY_CONNECTED`](https://nodejs.org/api/errors.html#errors_err_inspector_already_connected)
        -   [`ERR_INSPECTOR_CLOSED`](https://nodejs.org/api/errors.html#errors_err_inspector_closed)
        -   [`ERR_INSPECTOR_COMMAND`](https://nodejs.org/api/errors.html#errors_err_inspector_command)
        -   [`ERR_INSPECTOR_NOT_ACTIVE`](https://nodejs.org/api/errors.html#errors_err_inspector_not_active)
        -   [`ERR_INSPECTOR_NOT_AVAILABLE`](https://nodejs.org/api/errors.html#errors_err_inspector_not_available)
        -   [`ERR_INSPECTOR_NOT_CONNECTED`](https://nodejs.org/api/errors.html#errors_err_inspector_not_connected)
        -   [`ERR_INSPECTOR_NOT_WORKER`](https://nodejs.org/api/errors.html#errors_err_inspector_not_worker)
        -   [`ERR_INVALID_ADDRESS_FAMILY`](https://nodejs.org/api/errors.html#errors_err_invalid_address_family)
        -   [`ERR_INVALID_ARG_TYPE`](https://nodejs.org/api/errors.html#errors_err_invalid_arg_type)
        -   [`ERR_INVALID_ARG_VALUE`](https://nodejs.org/api/errors.html#errors_err_invalid_arg_value)
        -   [`ERR_INVALID_ASYNC_ID`](https://nodejs.org/api/errors.html#errors_err_invalid_async_id)
        -   [`ERR_INVALID_BUFFER_SIZE`](https://nodejs.org/api/errors.html#errors_err_invalid_buffer_size)
        -   [`ERR_INVALID_CALLBACK`](https://nodejs.org/api/errors.html#errors_err_invalid_callback)
        -   [`ERR_INVALID_CHAR`](https://nodejs.org/api/errors.html#errors_err_invalid_char)
        -   [`ERR_INVALID_CURSOR_POS`](https://nodejs.org/api/errors.html#errors_err_invalid_cursor_pos)
        -   [`ERR_INVALID_FD`](https://nodejs.org/api/errors.html#errors_err_invalid_fd)
        -   [`ERR_INVALID_FD_TYPE`](https://nodejs.org/api/errors.html#errors_err_invalid_fd_type)
        -   [`ERR_INVALID_FILE_URL_HOST`](https://nodejs.org/api/errors.html#errors_err_invalid_file_url_host)
        -   [`ERR_INVALID_FILE_URL_PATH`](https://nodejs.org/api/errors.html#errors_err_invalid_file_url_path)
        -   [`ERR_INVALID_HANDLE_TYPE`](https://nodejs.org/api/errors.html#errors_err_invalid_handle_type)
        -   [`ERR_INVALID_HTTP_TOKEN`](https://nodejs.org/api/errors.html#errors_err_invalid_http_token)
        -   [`ERR_INVALID_IP_ADDRESS`](https://nodejs.org/api/errors.html#errors_err_invalid_ip_address)
        -   [`ERR_INVALID_MODULE_SPECIFIER`](https://nodejs.org/api/errors.html#errors_err_invalid_module_specifier)
        -   [`ERR_INVALID_OPT_VALUE`](https://nodejs.org/api/errors.html#errors_err_invalid_opt_value)
        -   [`ERR_INVALID_OPT_VALUE_ENCODING`](https://nodejs.org/api/errors.html#errors_err_invalid_opt_value_encoding)
        -   [`ERR_INVALID_PACKAGE_CONFIG`](https://nodejs.org/api/errors.html#errors_err_invalid_package_config)
        -   [`ERR_INVALID_PACKAGE_TARGET`](https://nodejs.org/api/errors.html#errors_err_invalid_package_target)
        -   [`ERR_INVALID_PERFORMANCE_MARK`](https://nodejs.org/api/errors.html#errors_err_invalid_performance_mark)
        -   [`ERR_INVALID_PROTOCOL`](https://nodejs.org/api/errors.html#errors_err_invalid_protocol)
        -   [`ERR_INVALID_REPL_EVAL_CONFIG`](https://nodejs.org/api/errors.html#errors_err_invalid_repl_eval_config)
        -   [`ERR_INVALID_REPL_INPUT`](https://nodejs.org/api/errors.html#errors_err_invalid_repl_input)
        -   [`ERR_INVALID_RETURN_PROPERTY`](https://nodejs.org/api/errors.html#errors_err_invalid_return_property)
        -   [`ERR_INVALID_RETURN_PROPERTY_VALUE`](https://nodejs.org/api/errors.html#errors_err_invalid_return_property_value)
        -   [`ERR_INVALID_RETURN_VALUE`](https://nodejs.org/api/errors.html#errors_err_invalid_return_value)
        -   [`ERR_INVALID_SYNC_FORK_INPUT`](https://nodejs.org/api/errors.html#errors_err_invalid_sync_fork_input)
        -   [`ERR_INVALID_THIS`](https://nodejs.org/api/errors.html#errors_err_invalid_this)
        -   [`ERR_INVALID_TRANSFER_OBJECT`](https://nodejs.org/api/errors.html#errors_err_invalid_transfer_object)
        -   [`ERR_INVALID_TUPLE`](https://nodejs.org/api/errors.html#errors_err_invalid_tuple)
        -   [`ERR_INVALID_URI`](https://nodejs.org/api/errors.html#errors_err_invalid_uri)
        -   [`ERR_INVALID_URL`](https://nodejs.org/api/errors.html#errors_err_invalid_url)
        -   [`ERR_INVALID_URL_SCHEME`](https://nodejs.org/api/errors.html#errors_err_invalid_url_scheme)
        -   [`ERR_IPC_CHANNEL_CLOSED`](https://nodejs.org/api/errors.html#errors_err_ipc_channel_closed)
        -   [`ERR_IPC_DISCONNECTED`](https://nodejs.org/api/errors.html#errors_err_ipc_disconnected)
        -   [`ERR_IPC_ONE_PIPE`](https://nodejs.org/api/errors.html#errors_err_ipc_one_pipe)
        -   [`ERR_IPC_SYNC_FORK`](https://nodejs.org/api/errors.html#errors_err_ipc_sync_fork)
        -   [`ERR_MANIFEST_ASSERT_INTEGRITY`](https://nodejs.org/api/errors.html#errors_err_manifest_assert_integrity)
        -   [`ERR_MANIFEST_DEPENDENCY_MISSING`](https://nodejs.org/api/errors.html#errors_err_manifest_dependency_missing)
        -   [`ERR_MANIFEST_INTEGRITY_MISMATCH`](https://nodejs.org/api/errors.html#errors_err_manifest_integrity_mismatch)
        -   [`ERR_MANIFEST_INVALID_RESOURCE_FIELD`](https://nodejs.org/api/errors.html#errors_err_manifest_invalid_resource_field)
        -   [`ERR_MANIFEST_PARSE_POLICY`](https://nodejs.org/api/errors.html#errors_err_manifest_parse_policy)
        -   [`ERR_MANIFEST_TDZ`](https://nodejs.org/api/errors.html#errors_err_manifest_tdz)
        -   [`ERR_MANIFEST_UNKNOWN_ONERROR`](https://nodejs.org/api/errors.html#errors_err_manifest_unknown_onerror)
        -   [`ERR_MEMORY_ALLOCATION_FAILED`](https://nodejs.org/api/errors.html#errors_err_memory_allocation_failed)
        -   [`ERR_MESSAGE_TARGET_CONTEXT_UNAVAILABLE`](https://nodejs.org/api/errors.html#errors_err_message_target_context_unavailable)
        -   [`ERR_METHOD_NOT_IMPLEMENTED`](https://nodejs.org/api/errors.html#errors_err_method_not_implemented)
        -   [`ERR_MISSING_ARGS`](https://nodejs.org/api/errors.html#errors_err_missing_args)
        -   [`ERR_MISSING_OPTION`](https://nodejs.org/api/errors.html#errors_err_missing_option)
        -   [`ERR_MISSING_MESSAGE_PORT_IN_TRANSFER_LIST`](https://nodejs.org/api/errors.html#errors_err_missing_message_port_in_transfer_list)
        -   [`ERR_MISSING_PASSPHRASE`](https://nodejs.org/api/errors.html#errors_err_missing_passphrase)
        -   [`ERR_MISSING_PLATFORM_FOR_WORKER`](https://nodejs.org/api/errors.html#errors_err_missing_platform_for_worker)
        -   [`ERR_MODULE_NOT_FOUND`](https://nodejs.org/api/errors.html#errors_err_module_not_found)
        -   [`ERR_MULTIPLE_CALLBACK`](https://nodejs.org/api/errors.html#errors_err_multiple_callback)
        -   [`ERR_NAPI_CONS_FUNCTION`](https://nodejs.org/api/errors.html#errors_err_napi_cons_function)
        -   [`ERR_NAPI_INVALID_DATAVIEW_ARGS`](https://nodejs.org/api/errors.html#errors_err_napi_invalid_dataview_args)
        -   [`ERR_NAPI_INVALID_TYPEDARRAY_ALIGNMENT`](https://nodejs.org/api/errors.html#errors_err_napi_invalid_typedarray_alignment)
        -   [`ERR_NAPI_INVALID_TYPEDARRAY_LENGTH`](https://nodejs.org/api/errors.html#errors_err_napi_invalid_typedarray_length)
        -   [`ERR_NAPI_TSFN_CALL_JS`](https://nodejs.org/api/errors.html#errors_err_napi_tsfn_call_js)
        -   [`ERR_NAPI_TSFN_GET_UNDEFINED`](https://nodejs.org/api/errors.html#errors_err_napi_tsfn_get_undefined)
        -   [`ERR_NAPI_TSFN_START_IDLE_LOOP`](https://nodejs.org/api/errors.html#errors_err_napi_tsfn_start_idle_loop)
        -   [`ERR_NAPI_TSFN_STOP_IDLE_LOOP`](https://nodejs.org/api/errors.html#errors_err_napi_tsfn_stop_idle_loop)
        -   [`ERR_NO_CRYPTO`](https://nodejs.org/api/errors.html#errors_err_no_crypto)
        -   [`ERR_NO_ICU`](https://nodejs.org/api/errors.html#errors_err_no_icu)
        -   [`ERR_NON_CONTEXT_AWARE_DISABLED`](https://nodejs.org/api/errors.html#errors_err_non_context_aware_disabled)
        -   [`ERR_OUT_OF_RANGE`](https://nodejs.org/api/errors.html#errors_err_out_of_range)
        -   [`ERR_PACKAGE_IMPORT_NOT_DEFINED`](https://nodejs.org/api/errors.html#errors_err_package_import_not_defined)
        -   [`ERR_PACKAGE_PATH_NOT_EXPORTED`](https://nodejs.org/api/errors.html#errors_err_package_path_not_exported)
        -   [`ERR_PROTO_ACCESS`](https://nodejs.org/api/errors.html#errors_err_proto_access)
        -   [`ERR_REQUIRE_ESM`](https://nodejs.org/api/errors.html#errors_err_require_esm)
        -   [`ERR_SCRIPT_EXECUTION_INTERRUPTED`](https://nodejs.org/api/errors.html#errors_err_script_execution_interrupted)
        -   [`ERR_SCRIPT_EXECUTION_TIMEOUT`](https://nodejs.org/api/errors.html#errors_err_script_execution_timeout)
        -   [`ERR_SERVER_ALREADY_LISTEN`](https://nodejs.org/api/errors.html#errors_err_server_already_listen)
        -   [`ERR_SERVER_NOT_RUNNING`](https://nodejs.org/api/errors.html#errors_err_server_not_running)
        -   [`ERR_SOCKET_ALREADY_BOUND`](https://nodejs.org/api/errors.html#errors_err_socket_already_bound)
        -   [`ERR_SOCKET_BAD_BUFFER_SIZE`](https://nodejs.org/api/errors.html#errors_err_socket_bad_buffer_size)
        -   [`ERR_SOCKET_BAD_PORT`](https://nodejs.org/api/errors.html#errors_err_socket_bad_port)
        -   [`ERR_SOCKET_BAD_TYPE`](https://nodejs.org/api/errors.html#errors_err_socket_bad_type)
        -   [`ERR_SOCKET_BUFFER_SIZE`](https://nodejs.org/api/errors.html#errors_err_socket_buffer_size)
        -   [`ERR_SOCKET_CLOSED`](https://nodejs.org/api/errors.html#errors_err_socket_closed)
        -   [`ERR_SOCKET_DGRAM_IS_CONNECTED`](https://nodejs.org/api/errors.html#errors_err_socket_dgram_is_connected)
        -   [`ERR_SOCKET_DGRAM_NOT_CONNECTED`](https://nodejs.org/api/errors.html#errors_err_socket_dgram_not_connected)
        -   [`ERR_SOCKET_DGRAM_NOT_RUNNING`](https://nodejs.org/api/errors.html#errors_err_socket_dgram_not_running)
        -   [`ERR_SRI_PARSE`](https://nodejs.org/api/errors.html#errors_err_sri_parse)
        -   [`ERR_STREAM_CANNOT_PIPE`](https://nodejs.org/api/errors.html#errors_err_stream_cannot_pipe)
        -   [`ERR_STREAM_DESTROYED`](https://nodejs.org/api/errors.html#errors_err_stream_destroyed)
        -   [`ERR_STREAM_ALREADY_FINISHED`](https://nodejs.org/api/errors.html#errors_err_stream_already_finished)
        -   [`ERR_STREAM_NULL_VALUES`](https://nodejs.org/api/errors.html#errors_err_stream_null_values)
        -   [`ERR_STREAM_PREMATURE_CLOSE`](https://nodejs.org/api/errors.html#errors_err_stream_premature_close)
        -   [`ERR_STREAM_PUSH_AFTER_EOF`](https://nodejs.org/api/errors.html#errors_err_stream_push_after_eof)
        -   [`ERR_STREAM_UNSHIFT_AFTER_END_EVENT`](https://nodejs.org/api/errors.html#errors_err_stream_unshift_after_end_event)
        -   [`ERR_STREAM_WRAP`](https://nodejs.org/api/errors.html#errors_err_stream_wrap)
        -   [`ERR_STREAM_WRITE_AFTER_END`](https://nodejs.org/api/errors.html#errors_err_stream_write_after_end)
        -   [`ERR_STRING_TOO_LONG`](https://nodejs.org/api/errors.html#errors_err_string_too_long)
        -   [`ERR_SYNTHETIC`](https://nodejs.org/api/errors.html#errors_err_synthetic)
        -   [`ERR_SYSTEM_ERROR`](https://nodejs.org/api/errors.html#errors_err_system_error)
        -   [`ERR_TLS_CERT_ALTNAME_INVALID`](https://nodejs.org/api/errors.html#errors_err_tls_cert_altname_invalid)
        -   [`ERR_TLS_DH_PARAM_SIZE`](https://nodejs.org/api/errors.html#errors_err_tls_dh_param_size)
        -   [`ERR_TLS_HANDSHAKE_TIMEOUT`](https://nodejs.org/api/errors.html#errors_err_tls_handshake_timeout)
        -   [`ERR_TLS_INVALID_CONTEXT`](https://nodejs.org/api/errors.html#errors_err_tls_invalid_context)
        -   [`ERR_TLS_INVALID_STATE`](https://nodejs.org/api/errors.html#errors_err_tls_invalid_state)
        -   [`ERR_TLS_INVALID_PROTOCOL_METHOD`](https://nodejs.org/api/errors.html#errors_err_tls_invalid_protocol_method)
        -   [`ERR_TLS_INVALID_PROTOCOL_VERSION`](https://nodejs.org/api/errors.html#errors_err_tls_invalid_protocol_version)
        -   [`ERR_TLS_PROTOCOL_VERSION_CONFLICT`](https://nodejs.org/api/errors.html#errors_err_tls_protocol_version_conflict)
        -   [`ERR_TLS_RENEGOTIATION_DISABLED`](https://nodejs.org/api/errors.html#errors_err_tls_renegotiation_disabled)
        -   [`ERR_TLS_REQUIRED_SERVER_NAME`](https://nodejs.org/api/errors.html#errors_err_tls_required_server_name)
        -   [`ERR_TLS_SESSION_ATTACK`](https://nodejs.org/api/errors.html#errors_err_tls_session_attack)
        -   [`ERR_TLS_SNI_FROM_SERVER`](https://nodejs.org/api/errors.html#errors_err_tls_sni_from_server)
        -   [`ERR_TLS_PSK_SET_IDENTIY_HINT_FAILED`](https://nodejs.org/api/errors.html#errors_err_tls_psk_set_identiy_hint_failed)
        -   [`ERR_TRACE_EVENTS_CATEGORY_REQUIRED`](https://nodejs.org/api/errors.html#errors_err_trace_events_category_required)
        -   [`ERR_TRACE_EVENTS_UNAVAILABLE`](https://nodejs.org/api/errors.html#errors_err_trace_events_unavailable)
        -   [`ERR_TRANSFORM_ALREADY_TRANSFORMING`](https://nodejs.org/api/errors.html#errors_err_transform_already_transforming)
        -   [`ERR_TRANSFORM_WITH_LENGTH_0`](https://nodejs.org/api/errors.html#errors_err_transform_with_length_0)
        -   [`ERR_TTY_INIT_FAILED`](https://nodejs.org/api/errors.html#errors_err_tty_init_failed)
        -   [`ERR_UNAVAILABLE_DURING_EXIT`](https://nodejs.org/api/errors.html#errors_err_unavailable_during_exit)
        -   [`ERR_UNCAUGHT_EXCEPTION_CAPTURE_ALREADY_SET`](https://nodejs.org/api/errors.html#errors_err_uncaught_exception_capture_already_set)
        -   [`ERR_UNESCAPED_CHARACTERS`](https://nodejs.org/api/errors.html#errors_err_unescaped_characters)
        -   [`ERR_UNHANDLED_ERROR`](https://nodejs.org/api/errors.html#errors_err_unhandled_error)
        -   [`ERR_UNKNOWN_BUILTIN_MODULE`](https://nodejs.org/api/errors.html#errors_err_unknown_builtin_module)
        -   [`ERR_UNKNOWN_CREDENTIAL`](https://nodejs.org/api/errors.html#errors_err_unknown_credential)
        -   [`ERR_UNKNOWN_ENCODING`](https://nodejs.org/api/errors.html#errors_err_unknown_encoding)
        -   [`ERR_UNKNOWN_FILE_EXTENSION`](https://nodejs.org/api/errors.html#errors_err_unknown_file_extension)
        -   [`ERR_UNKNOWN_MODULE_FORMAT`](https://nodejs.org/api/errors.html#errors_err_unknown_module_format)
        -   [`ERR_UNKNOWN_SIGNAL`](https://nodejs.org/api/errors.html#errors_err_unknown_signal)
        -   [`ERR_UNSUPPORTED_DIR_IMPORT`](https://nodejs.org/api/errors.html#errors_err_unsupported_dir_import)
        -   [`ERR_UNSUPPORTED_ESM_URL_SCHEME`](https://nodejs.org/api/errors.html#errors_err_unsupported_esm_url_scheme)
        -   [`ERR_VALID_PERFORMANCE_ENTRY_TYPE`](https://nodejs.org/api/errors.html#errors_err_valid_performance_entry_type)
        -   [`ERR_VM_DYNAMIC_IMPORT_CALLBACK_MISSING`](https://nodejs.org/api/errors.html#errors_err_vm_dynamic_import_callback_missing)
        -   [`ERR_VM_MODULE_ALREADY_LINKED`](https://nodejs.org/api/errors.html#errors_err_vm_module_already_linked)
        -   [`ERR_VM_MODULE_CACHED_DATA_REJECTED`](https://nodejs.org/api/errors.html#errors_err_vm_module_cached_data_rejected)
        -   [`ERR_VM_MODULE_CANNOT_CREATE_CACHED_DATA`](https://nodejs.org/api/errors.html#errors_err_vm_module_cannot_create_cached_data)
        -   [`ERR_VM_MODULE_DIFFERENT_CONTEXT`](https://nodejs.org/api/errors.html#errors_err_vm_module_different_context)
        -   [`ERR_VM_MODULE_LINKING_ERRORED`](https://nodejs.org/api/errors.html#errors_err_vm_module_linking_errored)
        -   [`ERR_VM_MODULE_NOT_MODULE`](https://nodejs.org/api/errors.html#errors_err_vm_module_not_module)
        -   [`ERR_VM_MODULE_STATUS`](https://nodejs.org/api/errors.html#errors_err_vm_module_status)
        -   [`ERR_WASI_ALREADY_STARTED`](https://nodejs.org/api/errors.html#errors_err_wasi_already_started)
        -   [`ERR_WASI_NOT_STARTED`](https://nodejs.org/api/errors.html#errors_err_wasi_not_started)
        -   [`ERR_WORKER_INIT_FAILED`](https://nodejs.org/api/errors.html#errors_err_worker_init_failed)
        -   [`ERR_WORKER_INVALID_EXEC_ARGV`](https://nodejs.org/api/errors.html#errors_err_worker_invalid_exec_argv)
        -   [`ERR_WORKER_NOT_RUNNING`](https://nodejs.org/api/errors.html#errors_err_worker_not_running)
        -   [`ERR_WORKER_OUT_OF_MEMORY`](https://nodejs.org/api/errors.html#errors_err_worker_out_of_memory)
        -   [`ERR_WORKER_PATH`](https://nodejs.org/api/errors.html#errors_err_worker_path)
        -   [`ERR_WORKER_UNSERIALIZABLE_ERROR`](https://nodejs.org/api/errors.html#errors_err_worker_unserializable_error)
        -   [`ERR_WORKER_UNSUPPORTED_EXTENSION`](https://nodejs.org/api/errors.html#errors_err_worker_unsupported_extension)
        -   [`ERR_WORKER_UNSUPPORTED_OPERATION`](https://nodejs.org/api/errors.html#errors_err_worker_unsupported_operation)
        -   [`ERR_ZLIB_INITIALIZATION_FAILED`](https://nodejs.org/api/errors.html#errors_err_zlib_initialization_failed)
        -   [`HPE_HEADER_OVERFLOW`](https://nodejs.org/api/errors.html#errors_hpe_header_overflow)
        -   [`HPE_UNEXPECTED_CONTENT_LENGTH`](https://nodejs.org/api/errors.html#errors_hpe_unexpected_content_length)
        -   [`MODULE_NOT_FOUND`](https://nodejs.org/api/errors.html#errors_module_not_found)

    -   [Legacy Node.js error
        codes](https://nodejs.org/api/errors.html#errors_legacy_node_js_error_codes)

        -   [`ERR_CANNOT_TRANSFER_OBJECT`](https://nodejs.org/api/errors.html#errors_err_cannot_transfer_object)
        -   [`ERR_CLOSED_MESSAGE_PORT`](https://nodejs.org/api/errors.html#errors_err_closed_message_port)
        -   [`ERR_CRYPTO_HASH_DIGEST_NO_UTF16`](https://nodejs.org/api/errors.html#errors_err_crypto_hash_digest_no_utf16)
        -   [`ERR_HTTP2_FRAME_ERROR`](https://nodejs.org/api/errors.html#errors_err_http2_frame_error)
        -   [`ERR_HTTP2_HEADERS_OBJECT`](https://nodejs.org/api/errors.html#errors_err_http2_headers_object)
        -   [`ERR_HTTP2_HEADER_REQUIRED`](https://nodejs.org/api/errors.html#errors_err_http2_header_required)
        -   [`ERR_HTTP2_INFO_HEADERS_AFTER_RESPOND`](https://nodejs.org/api/errors.html#errors_err_http2_info_headers_after_respond)
        -   [`ERR_HTTP2_STREAM_CLOSED`](https://nodejs.org/api/errors.html#errors_err_http2_stream_closed)
        -   [`ERR_HTTP_INVALID_CHAR`](https://nodejs.org/api/errors.html#errors_err_http_invalid_char)
        -   [`ERR_INDEX_OUT_OF_RANGE`](https://nodejs.org/api/errors.html#errors_err_index_out_of_range)
        -   [`ERR_NAPI_CONS_PROTOTYPE_OBJECT`](https://nodejs.org/api/errors.html#errors_err_napi_cons_prototype_object)
        -   [`ERR_NO_LONGER_SUPPORTED`](https://nodejs.org/api/errors.html#errors_err_no_longer_supported)
        -   [`ERR_OUTOFMEMORY`](https://nodejs.org/api/errors.html#errors_err_outofmemory)
        -   [`ERR_PARSE_HISTORY_DATA`](https://nodejs.org/api/errors.html#errors_err_parse_history_data)
        -   [`ERR_SOCKET_CANNOT_SEND`](https://nodejs.org/api/errors.html#errors_err_socket_cannot_send)
        -   [`ERR_STDERR_CLOSE`](https://nodejs.org/api/errors.html#errors_err_stderr_close)
        -   [`ERR_STDOUT_CLOSE`](https://nodejs.org/api/errors.html#errors_err_stdout_close)
        -   [`ERR_STREAM_READ_NOT_IMPLEMENTED`](https://nodejs.org/api/errors.html#errors_err_stream_read_not_implemented)
        -   [`ERR_TLS_RENEGOTIATION_FAILED`](https://nodejs.org/api/errors.html#errors_err_tls_renegotiation_failed)
        -   [`ERR_TRANSFERRING_EXTERNALIZED_SHAREDARRAYBUFFER`](https://nodejs.org/api/errors.html#errors_err_transferring_externalized_sharedarraybuffer)
        -   [`ERR_UNKNOWN_STDIN_TYPE`](https://nodejs.org/api/errors.html#errors_err_unknown_stdin_type)
        -   [`ERR_UNKNOWN_STREAM_TYPE`](https://nodejs.org/api/errors.html#errors_err_unknown_stream_type)
        -   [`ERR_V8BREAKITERATOR`](https://nodejs.org/api/errors.html#errors_err_v8breakiterator)
        -   [`ERR_VALUE_OUT_OF_RANGE`](https://nodejs.org/api/errors.html#errors_err_value_out_of_range)
        -   [`ERR_VM_MODULE_NOT_LINKED`](https://nodejs.org/api/errors.html#errors_err_vm_module_not_linked)
        -   [`ERR_ZLIB_BINDING_CLOSED`](https://nodejs.org/api/errors.html#errors_err_zlib_binding_closed)

Errors[\#](https://nodejs.org/api/errors.html#errors_errors)
============================================================

Applications running in Node.js will generally experience four
categories of errors:

-   Standard JavaScript errors such as
    [\<EvalError\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError),
    [\<SyntaxError\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError),
    [\<RangeError\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError),
    [\<ReferenceError\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError),
    [\<TypeError\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError),
    and
    [\<URIError\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/URIError).
-   System errors triggered by underlying operating system constraints
    such as attempting to open a file that does not exist or attempting
    to send data over a closed socket.
-   User-specified errors triggered by application code.
-   `AssertionError`s are a special class of error that can be triggered
    when Node.js detects an exceptional logic violation that should
    never occur. These are raised typically by the `assert` module.

All JavaScript and system errors raised by Node.js inherit from, or are
instances of, the standard JavaScript
[\<Error\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)
class and are guaranteed to provide *at least* the properties available
on that class.

Error propagation and interception[\#](https://nodejs.org/api/errors.html#errors_error_propagation_and_interception)
--------------------------------------------------------------------------------------------------------------------

Node.js supports several mechanisms for propagating and handling errors
that occur while an application is running. How these errors are
reported and handled depends entirely on the type of `Error` and the
style of the API that is called.

All JavaScript errors are handled as exceptions that *immediately*
generate and throw an error using the standard JavaScript `throw`
mechanism. These are handled using the [`try…catch`
construct](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch)
provided by the JavaScript language.

    // Throws with a ReferenceError because z is not defined.
    try {
      const m = 1;
      const n = m + z;
    } catch (err) {
      // Handle the error here.
    }

Any use of the JavaScript `throw` mechanism will raise an exception that
*must* be handled using `try…catch` or the Node.js process will exit
immediately.

With few exceptions, *Synchronous* APIs (any blocking method that does
not accept a `callback` function, such as
[`fs.readFileSync`](https://nodejs.org/api/fs.html#fs_fs_readfilesync_path_options)),
will use `throw` to report errors.

Errors that occur within *Asynchronous APIs* may be reported in multiple
ways:

-   Most asynchronous methods that accept a `callback` function will
    accept an `Error` object passed as the first argument to that
    function. If that first argument is not `null` and is an instance of
    `Error`, then an error occurred that should be handled.

<!-- -->

    const fs = require('fs');
    fs.readFile('a file that does not exist', (err, data) => {
      if (err) {
        console.error('There was an error reading the file!', err);
        return;
      }
      // Otherwise handle the data
    });

-   When an asynchronous method is called on an object that is an
    [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter),
    errors can be routed to that object's `'error'` event.

        const net = require('net');
        const connection = net.connect('localhost');

        // Adding an 'error' event handler to a stream:
        connection.on('error', (err) => {
          // If the connection is reset by the server, or if it can't
          // connect at all, or on any sort of error encountered by
          // the connection, the error will be sent here.
          console.error(err);
        });

        connection.pipe(process.stdout);

-   A handful of typically asynchronous methods in the Node.js API may
    still use the `throw` mechanism to raise exceptions that must be
    handled using `try…catch`. There is no comprehensive list of such
    methods; please refer to the documentation of each method to
    determine the appropriate error handling mechanism required.

The use of the `'error'` event mechanism is most common for
[stream-based](https://nodejs.org/api/stream.html) and [event
emitter-based](https://nodejs.org/api/events.html#events_class_eventemitter)
APIs, which themselves represent a series of asynchronous operations
over time (as opposed to a single operation that may pass or fail).

For *all*
[`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)
objects, if an `'error'` event handler is not provided, the error will
be thrown, causing the Node.js process to report an uncaught exception
and crash unless either: The
[`domain`](https://nodejs.org/api/domain.html) module is used
appropriately or a handler has been registered for the
[`'uncaughtException'`](https://nodejs.org/api/process.html#process_event_uncaughtexception)
event.

    const EventEmitter = require('events');
    const ee = new EventEmitter();

    setImmediate(() => {
      // This will crash the process because no 'error' event
      // handler has been added.
      ee.emit('error', new Error('This will crash'));
    });

Errors generated in this way *cannot* be intercepted using `try…catch`
as they are thrown *after* the calling code has already exited.

Developers must refer to the documentation for each method to determine
exactly how errors raised by those methods are propagated.

### Error-first callbacks[\#](https://nodejs.org/api/errors.html#errors_error_first_callbacks)

Most asynchronous methods exposed by the Node.js core API follow an
idiomatic pattern referred to as an *error-first callback*. With this
pattern, a callback function is passed to the method as an argument.
When the operation either completes or an error is raised, the callback
function is called with the `Error` object (if any) passed as the first
argument. If no error was raised, the first argument will be passed as
`null`.

    const fs = require('fs');

    function errorFirstCallback(err, data) {
      if (err) {
        console.error('There was an error', err);
        return;
      }
      console.log(data);
    }

    fs.readFile('/some/file/that/does-not-exist', errorFirstCallback);
    fs.readFile('/some/file/that/does-exist', errorFirstCallback);

The JavaScript `try…catch` mechanism **cannot** be used to intercept
errors generated by asynchronous APIs. A common mistake for beginners is
to try to use `throw` inside an error-first callback:

    // THIS WILL NOT WORK:
    const fs = require('fs');

    try {
      fs.readFile('/some/file/that/does-not-exist', (err, data) => {
        // Mistaken assumption: throwing here...
        if (err) {
          throw err;
        }
      });
    } catch (err) {
      // This will not catch the throw!
      console.error(err);
    }

This will not work because the callback function passed to
`fs.readFile()` is called asynchronously. By the time the callback has
been called, the surrounding code, including the `try…catch` block, will
have already exited. Throwing an error inside the callback **can crash
the Node.js process** in most cases. If
[domains](https://nodejs.org/api/domain.html) are enabled, or a handler
has been registered with `process.on('uncaughtException')`, such errors
can be intercepted.

Class: `Error`[\#](https://nodejs.org/api/errors.html#errors_class_error)
-------------------------------------------------------------------------

A generic JavaScript
[\<Error\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)
object that does not denote any specific circumstance of why the error
occurred. `Error` objects capture a "stack trace" detailing the point in
the code at which the `Error` was instantiated, and may provide a text
description of the error.

All errors generated by Node.js, including all system and JavaScript
errors, will either be instances of, or inherit from, the `Error` class.

### `new Error(message)`[\#](https://nodejs.org/api/errors.html#errors_new_error_message)

-   `message`
    [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

Creates a new `Error` object and sets the `error.message` property to
the provided text message. If an object is passed as `message`, the text
message is generated by calling `message.toString()`. The `error.stack`
property will represent the point in the code at which `new Error()` was
called. Stack traces are dependent on [V8's stack trace
API](https://github.com/v8/v8/wiki/Stack-Trace-API). Stack traces extend
only to either (a) the beginning of *synchronous code execution*, or (b)
the number of frames given by the property `Error.stackTraceLimit`,
whichever is smaller.

### `Error.captureStackTrace(targetObject[, constructorOpt])`[\#](https://nodejs.org/api/errors.html#errors_error_capturestacktrace_targetobject_constructoropt)

-   `targetObject`
    [\<Object\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
-   `constructorOpt`
    [\<Function\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function)

Creates a `.stack` property on `targetObject`, which when accessed
returns a string representing the location in the code at which
`Error.captureStackTrace()` was called.

    const myObject = {};
    Error.captureStackTrace(myObject);
    myObject.stack;  // Similar to `new Error().stack`

The first line of the trace will be prefixed with
`${myObject.name}: ${myObject.message}`.

The optional `constructorOpt` argument accepts a function. If given, all
frames above `constructorOpt`, including `constructorOpt`, will be
omitted from the generated stack trace.

The `constructorOpt` argument is useful for hiding implementation
details of error generation from an end user. For instance:

    function MyError() {
      Error.captureStackTrace(this, MyError);
    }

    // Without passing MyError to captureStackTrace, the MyError
    // frame would show up in the .stack property. By passing
    // the constructor, we omit that frame, and retain all frames below it.
    new MyError().stack;

### `Error.stackTraceLimit`[\#](https://nodejs.org/api/errors.html#errors_error_stacktracelimit)

-   [\<number\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)

The `Error.stackTraceLimit` property specifies the number of stack
frames collected by a stack trace (whether generated by
`new Error().stack` or `Error.captureStackTrace(obj)`).

The default value is `10` but may be set to any valid JavaScript number.
Changes will affect any stack trace captured *after* the value has been
changed.

If set to a non-number value, or set to a negative number, stack traces
will not capture any frames.

### `error.code`[\#](https://nodejs.org/api/errors.html#errors_error_code)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

The `error.code` property is a string label that identifies the kind of
error. `error.code` is the most stable way to identify an error. It will
only change between major versions of Node.js. In contrast,
`error.message` strings may change between any versions of Node.js. See
[Node.js error
codes](https://nodejs.org/api/errors.html#nodejs-error-codes) for
details about specific codes.

### `error.message`[\#](https://nodejs.org/api/errors.html#errors_error_message)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

The `error.message` property is the string description of the error as
set by calling `new Error(message)`. The `message` passed to the
constructor will also appear in the first line of the stack trace of the
`Error`, however changing this property after the `Error` object is
created *may not* change the first line of the stack trace (for example,
when `error.stack` is read before this property is changed).

    const err = new Error('The message');
    console.error(err.message);
    // Prints: The message

### `error.stack`[\#](https://nodejs.org/api/errors.html#errors_error_stack)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

The `error.stack` property is a string describing the point in the code
at which the `Error` was instantiated.

    Error: Things keep happening!
       at /home/gbusey/file.js:525:2
       at Frobnicator.refrobulate (/home/gbusey/business-logic.js:424:21)
       at Actor.<anonymous> (/home/gbusey/actors.js:400:8)
       at increaseSynergy (/home/gbusey/actors.js:701:6)

The first line is formatted as `<error class name>: <error message>`,
and is followed by a series of stack frames (each line beginning with
"at "). Each frame describes a call site within the code that lead to
the error being generated. V8 attempts to display a name for each
function (by variable name, function name, or object method name), but
occasionally it will not be able to find a suitable name. If V8 cannot
determine a name for the function, only location information will be
displayed for that frame. Otherwise, the determined function name will
be displayed with location information appended in parentheses.

Frames are only generated for JavaScript functions. If, for example,
execution synchronously passes through a C++ addon function called
`cheetahify` which itself calls a JavaScript function, the frame
representing the `cheetahify` call will not be present in the stack
traces:

    const cheetahify = require('./native-binding.node');

    function makeFaster() {
      // `cheetahify()` *synchronously* calls speedy.
      cheetahify(function speedy() {
        throw new Error('oh no!');
      });
    }

    makeFaster();
    // will throw:
    //   /home/gbusey/file.js:6
    //       throw new Error('oh no!');
    //           ^
    //   Error: oh no!
    //       at speedy (/home/gbusey/file.js:6:11)
    //       at makeFaster (/home/gbusey/file.js:5:3)
    //       at Object.<anonymous> (/home/gbusey/file.js:10:1)
    //       at Module._compile (module.js:456:26)
    //       at Object.Module._extensions..js (module.js:474:10)
    //       at Module.load (module.js:356:32)
    //       at Function.Module._load (module.js:312:12)
    //       at Function.Module.runMain (module.js:497:10)
    //       at startup (node.js:119:16)
    //       at node.js:906:3

The location information will be one of:

-   `native`, if the frame represents a call internal to V8 (as in
    `[].forEach`).
-   `plain-filename.js:line:column`, if the frame represents a call
    internal to Node.js.
-   `/absolute/path/to/file.js:line:column`, if the frame represents a
    call in a user program, or its dependencies.

The string representing the stack trace is lazily generated when the
`error.stack` property is **accessed**.

The number of frames captured by the stack trace is bounded by the
smaller of `Error.stackTraceLimit` or the number of available frames on
the current event loop tick.

Class: `AssertionError`[\#](https://nodejs.org/api/errors.html#errors_class_assertionerror)
-------------------------------------------------------------------------------------------

-   Extends:
    [\<errors.Error\>](https://nodejs.org/api/errors.html#errors_class_error)

Indicates the failure of an assertion. For details, see
[`Class: assert.AssertionError`](https://nodejs.org/api/assert.html#assert_class_assert_assertionerror).

Class: `RangeError`[\#](https://nodejs.org/api/errors.html#errors_class_rangeerror)
-----------------------------------------------------------------------------------

-   Extends:
    [\<errors.Error\>](https://nodejs.org/api/errors.html#errors_class_error)

Indicates that a provided argument was not within the set or range of
acceptable values for a function; whether that is a numeric range, or
outside the set of options for a given function parameter.

    require('net').connect(-1);
    // Throws "RangeError: "port" option should be >= 0 and < 65536: -1"

Node.js will generate and throw `RangeError` instances *immediately* as
a form of argument validation.

Class: `ReferenceError`[\#](https://nodejs.org/api/errors.html#errors_class_referenceerror)
-------------------------------------------------------------------------------------------

-   Extends:
    [\<errors.Error\>](https://nodejs.org/api/errors.html#errors_class_error)

Indicates that an attempt is being made to access a variable that is not
defined. Such errors commonly indicate typos in code, or an otherwise
broken program.

While client code may generate and propagate these errors, in practice,
only V8 will do so.

    doesNotExist;
    // Throws ReferenceError, doesNotExist is not a variable in this program.

Unless an application is dynamically generating and running code,
`ReferenceError` instances indicate a bug in the code or its
dependencies.

Class: `SyntaxError`[\#](https://nodejs.org/api/errors.html#errors_class_syntaxerror)
-------------------------------------------------------------------------------------

-   Extends:
    [\<errors.Error\>](https://nodejs.org/api/errors.html#errors_class_error)

Indicates that a program is not valid JavaScript. These errors may only
be generated and propagated as a result of code evaluation. Code
evaluation may happen as a result of `eval`, `Function`, `require`, or
[vm](https://nodejs.org/api/vm.html). These errors are almost always
indicative of a broken program.

    try {
      require('vm').runInThisContext('binary ! isNotOk');
    } catch (err) {
      // 'err' will be a SyntaxError.
    }

`SyntaxError` instances are unrecoverable in the context that created
them – they may only be caught by other contexts.

Class: `SystemError`[\#](https://nodejs.org/api/errors.html#errors_class_systemerror)
-------------------------------------------------------------------------------------

-   Extends:
    [\<errors.Error\>](https://nodejs.org/api/errors.html#errors_class_error)

Node.js generates system errors when exceptions occur within its runtime
environment. These usually occur when an application violates an
operating system constraint. For example, a system error will occur if
an application attempts to read a file that does not exist.

-   `address`
    [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)
    If present, the address to which a network connection failed
-   `code`
    [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)
    The string error code
-   `dest`
    [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)
    If present, the file path destination when reporting a file system
    error
-   `errno`
    [\<number\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)
    The system-provided error number
-   `info`
    [\<Object\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
    If present, extra details about the error condition
-   `message`
    [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)
    A system-provided human-readable description of the error
-   `path`
    [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)
    If present, the file path when reporting a file system error
-   `port`
    [\<number\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)
    If present, the network connection port that is not available
-   `syscall`
    [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)
    The name of the system call that triggered the error

### `error.address`[\#](https://nodejs.org/api/errors.html#errors_error_address)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

If present, `error.address` is a string describing the address to which
a network connection failed.

### `error.code`[\#](https://nodejs.org/api/errors.html#errors_error_code_1)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

The `error.code` property is a string representing the error code.

### `error.dest`[\#](https://nodejs.org/api/errors.html#errors_error_dest)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

If present, `error.dest` is the file path destination when reporting a
file system error.

### `error.errno`[\#](https://nodejs.org/api/errors.html#errors_error_errno)

-   [\<number\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)

The `error.errno` property is a negative number which corresponds to the
error code defined in
[`libuv Error handling`](https://docs.libuv.org/en/v1.x/errors.html).

On Windows the error number provided by the system will be normalized by
libuv.

To get the string representation of the error code, use
[`util.getSystemErrorName(error.errno)`](https://nodejs.org/api/util.html#util_util_getsystemerrorname_err).

### `error.info`[\#](https://nodejs.org/api/errors.html#errors_error_info)

-   [\<Object\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

If present, `error.info` is an object with details about the error
condition.

### `error.message`[\#](https://nodejs.org/api/errors.html#errors_error_message_1)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

`error.message` is a system-provided human-readable description of the
error.

### `error.path`[\#](https://nodejs.org/api/errors.html#errors_error_path)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

If present, `error.path` is a string containing a relevant invalid
pathname.

### `error.port`[\#](https://nodejs.org/api/errors.html#errors_error_port)

-   [\<number\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)

If present, `error.port` is the network connection port that is not
available.

### `error.syscall`[\#](https://nodejs.org/api/errors.html#errors_error_syscall)

-   [\<string\>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type)

The `error.syscall` property is a string describing the
[syscall](https://man7.org/linux/man-pages/man2/syscalls.2.html) that
failed.

### Common system errors[\#](https://nodejs.org/api/errors.html#errors_common_system_errors)

This is a list of system errors commonly-encountered when writing a
Node.js program. For a comprehensive list, see the [`errno`(3) man
page](https://man7.org/linux/man-pages/man3/errno.3.html).

-   `EACCES` (Permission denied): An attempt was made to access a file
    in a way forbidden by its file access permissions.

-   `EADDRINUSE` (Address already in use): An attempt to bind a server
    ([`net`](https://nodejs.org/api/net.html),
    [`http`](https://nodejs.org/api/http.html), or
    [`https`](https://nodejs.org/api/https.html)) to a local address
    failed due to another server on the local system already occupying
    that address.

-   `ECONNREFUSED` (Connection refused): No connection could be made
    because the target machine actively refused it. This usually results
    from trying to connect to a service that is inactive on the foreign
    host.

-   `ECONNRESET` (Connection reset by peer): A connection was forcibly
    closed by a peer. This normally results from a loss of the
    connection on the remote socket due to a timeout or reboot. Commonly
    encountered via the [`http`](https://nodejs.org/api/http.html) and
    [`net`](https://nodejs.org/api/net.html) modules.

-   `EEXIST` (File exists): An existing file was the target of an
    operation that required that the target not exist.

-   `EISDIR` (Is a directory): An operation expected a file, but the
    given pathname was a directory.

-   `EMFILE` (Too many open files in system): Maximum number of [file
    descriptors](https://en.wikipedia.org/wiki/File_descriptor)
    allowable on the system has been reached, and requests for another
    descriptor cannot be fulfilled until at least one has been closed.
    This is encountered when opening many files at once in parallel,
    especially on systems (in particular, macOS) where there is a low
    file descriptor limit for processes. To remedy a low limit, run
    `ulimit -n 2048` in the same shell that will run the Node.js
    process.

-   `ENOENT` (No such file or directory): Commonly raised by
    [`fs`](https://nodejs.org/api/fs.html) operations to indicate that a
    component of the specified pathname does not exist. No entity (file
    or directory) could be found by the given path.

-   `ENOTDIR` (Not a directory): A component of the given pathname
    existed, but was not a directory as expected. Commonly raised by
    [`fs.readdir`](https://nodejs.org/api/fs.html#fs_fs_readdir_path_options_callback).

-   `ENOTEMPTY` (Directory not empty): A directory with entries was the
    target of an operation that requires an empty directory, usually
    [`fs.unlink`](https://nodejs.org/api/fs.html#fs_fs_unlink_path_callback).

-   `ENOTFOUND` (DNS lookup failed): Indicates a DNS failure of either
    `EAI_NODATA` or `EAI_NONAME`. This is not a standard POSIX error.

-   `EPERM` (Operation not permitted): An attempt was made to perform an
    operation that requires elevated privileges.

-   `EPIPE` (Broken pipe): A write on a pipe, socket, or FIFO for which
    there is no process to read the data. Commonly encountered at the
    [`net`](https://nodejs.org/api/net.html) and
    [`http`](https://nodejs.org/api/http.html) layers, indicative that
    the remote side of the stream being written to has been closed.

-   `ETIMEDOUT` (Operation timed out): A connect or send request failed
    because the connected party did not properly respond after a period
    of time. Usually encountered by
    [`http`](https://nodejs.org/api/http.html) or
    [`net`](https://nodejs.org/api/net.html). Often a sign that a
    `socket.end()` was not properly called.

Class: `TypeError`[\#](https://nodejs.org/api/errors.html#errors_class_typeerror)
---------------------------------------------------------------------------------

-   Extends
    [\<errors.Error\>](https://nodejs.org/api/errors.html#errors_class_error)

Indicates that a provided argument is not an allowable type. For
example, passing a function to a parameter which expects a string would
be a `TypeError`.

    require('url').parse(() => { });
    // Throws TypeError, since it expected a string.

Node.js will generate and throw `TypeError` instances *immediately* as a
form of argument validation.

Exceptions vs. errors[\#](https://nodejs.org/api/errors.html#errors_exceptions_vs_errors)
-----------------------------------------------------------------------------------------

A JavaScript exception is a value that is thrown as a result of an
invalid operation or as the target of a `throw` statement. While it is
not required that these values are instances of `Error` or classes which
inherit from `Error`, all exceptions thrown by Node.js or the JavaScript
runtime *will* be instances of `Error`.

Some exceptions are *unrecoverable* at the JavaScript layer. Such
exceptions will *always* cause the Node.js process to crash. Examples
include `assert()` checks or `abort()` calls in the C++ layer.

OpenSSL errors[\#](https://nodejs.org/api/errors.html#errors_openssl_errors)
----------------------------------------------------------------------------

Errors originating in `crypto` or `tls` are of class `Error`, and in
addition to the standard `.code` and `.message` properties, may have
some additional OpenSSL-specific properties.

### `error.opensslErrorStack`[\#](https://nodejs.org/api/errors.html#errors_error_opensslerrorstack)

An array of errors that can give context to where in the OpenSSL library
an error originates from.

### `error.function`[\#](https://nodejs.org/api/errors.html#errors_error_function)

The OpenSSL function the error originates in.

### `error.library`[\#](https://nodejs.org/api/errors.html#errors_error_library)

The OpenSSL library the error originates in.

### `error.reason`[\#](https://nodejs.org/api/errors.html#errors_error_reason)

A human-readable string describing the reason for the error.

Node.js error codes[\#](https://nodejs.org/api/errors.html#errors_node_js_error_codes)
--------------------------------------------------------------------------------------

### `ERR_AMBIGUOUS_ARGUMENT`[\#](https://nodejs.org/api/errors.html#errors_err_ambiguous_argument)

A function argument is being used in a way that suggests that the
function signature may be misunderstood. This is thrown by the `assert`
module when the `message` parameter in `assert.throws(block, message)`
matches the error message thrown by `block` because that usage suggests
that the user believes `message` is the expected message rather than the
message the `AssertionError` will display if `block` does not throw.

### `ERR_ARG_NOT_ITERABLE`[\#](https://nodejs.org/api/errors.html#errors_err_arg_not_iterable)

An iterable argument (i.e. a value that works with `for...of` loops) was
required, but not provided to a Node.js API.

### `ERR_ASSERTION`[\#](https://nodejs.org/api/errors.html#errors_err_assertion)

A special type of error that can be triggered whenever Node.js detects
an exceptional logic violation that should never occur. These are raised
typically by the `assert` module.

### `ERR_ASYNC_CALLBACK`[\#](https://nodejs.org/api/errors.html#errors_err_async_callback)

An attempt was made to register something that is not a function as an
`AsyncHooks` callback.

### `ERR_ASYNC_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_async_type)

The type of an asynchronous resource was invalid. Users are also able to
define their own types if using the public embedder API.

### `ERR_BROTLI_COMPRESSION_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_brotli_compression_failed)

Data passed to a Brotli stream was not successfully compressed.

### `ERR_BROTLI_INVALID_PARAM`[\#](https://nodejs.org/api/errors.html#errors_err_brotli_invalid_param)

An invalid parameter key was passed during construction of a Brotli
stream.

### `ERR_BUFFER_CONTEXT_NOT_AVAILABLE`[\#](https://nodejs.org/api/errors.html#errors_err_buffer_context_not_available)

An attempt was made to create a Node.js `Buffer` instance from addon or
embedder code, while in a JS engine Context that is not associated with
a Node.js instance. The data passed to the `Buffer` method will have
been released by the time the method returns.

When encountering this error, a possible alternative to creating a
`Buffer` instance is to create a normal `Uint8Array`, which only differs
in the prototype of the resulting object. `Uint8Array`s are generally
accepted in all Node.js core APIs where `Buffer`s are; they are
available in all Contexts.

### `ERR_BUFFER_OUT_OF_BOUNDS`[\#](https://nodejs.org/api/errors.html#errors_err_buffer_out_of_bounds)

An operation outside the bounds of a `Buffer` was attempted.

### `ERR_BUFFER_TOO_LARGE`[\#](https://nodejs.org/api/errors.html#errors_err_buffer_too_large)

An attempt has been made to create a `Buffer` larger than the maximum
allowed size.

### `ERR_CANNOT_WATCH_SIGINT`[\#](https://nodejs.org/api/errors.html#errors_err_cannot_watch_sigint)

Node.js was unable to watch for the `SIGINT` signal.

### `ERR_CHILD_CLOSED_BEFORE_REPLY`[\#](https://nodejs.org/api/errors.html#errors_err_child_closed_before_reply)

A child process was closed before the parent received a reply.

### `ERR_CHILD_PROCESS_IPC_REQUIRED`[\#](https://nodejs.org/api/errors.html#errors_err_child_process_ipc_required)

Used when a child process is being forked without specifying an IPC
channel.

### `ERR_CHILD_PROCESS_STDIO_MAXBUFFER`[\#](https://nodejs.org/api/errors.html#errors_err_child_process_stdio_maxbuffer)

Used when the main process is trying to read data from the child
process's STDERR/STDOUT, and the data's length is longer than the
`maxBuffer` option.

### `ERR_CONSOLE_WRITABLE_STREAM`[\#](https://nodejs.org/api/errors.html#errors_err_console_writable_stream)

`Console` was instantiated without `stdout` stream, or `Console` has a
non-writable `stdout` or `stderr` stream.

### `ERR_CONTEXT_NOT_INITIALIZED`[\#](https://nodejs.org/api/errors.html#errors_err_context_not_initialized)

The vm context passed into the API is not yet initialized. This could
happen when an error occurs (and is caught) during the creation of the
context, for example, when the allocation fails or the maximum call
stack size is reached when the context is created.

### `ERR_CONSTRUCT_CALL_REQUIRED`[\#](https://nodejs.org/api/errors.html#errors_err_construct_call_required)

A constructor for a class was called without `new`.

### `ERR_CONSTRUCT_CALL_INVALID`[\#](https://nodejs.org/api/errors.html#errors_err_construct_call_invalid)

A class constructor was called that is not callable.

### `ERR_CPU_USAGE`[\#](https://nodejs.org/api/errors.html#errors_err_cpu_usage)

The native call from `process.cpuUsage` could not be processed.

### `ERR_CRYPTO_CUSTOM_ENGINE_NOT_SUPPORTED`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_custom_engine_not_supported)

A client certificate engine was requested that is not supported by the
version of OpenSSL being used.

### `ERR_CRYPTO_ECDH_INVALID_FORMAT`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_ecdh_invalid_format)

An invalid value for the `format` argument was passed to the
`crypto.ECDH()` class `getPublicKey()` method.

### `ERR_CRYPTO_ECDH_INVALID_PUBLIC_KEY`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_ecdh_invalid_public_key)

An invalid value for the `key` argument has been passed to the
`crypto.ECDH()` class `computeSecret()` method. It means that the public
key lies outside of the elliptic curve.

### `ERR_CRYPTO_ENGINE_UNKNOWN`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_engine_unknown)

An invalid crypto engine identifier was passed to
[`require('crypto').setEngine()`](https://nodejs.org/api/crypto.html#crypto_crypto_setengine_engine_flags).

### `ERR_CRYPTO_FIPS_FORCED`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_fips_forced)

The [`--force-fips`](https://nodejs.org/api/cli.html#cli_force_fips)
command-line argument was used but there was an attempt to enable or
disable FIPS mode in the `crypto` module.

### `ERR_CRYPTO_FIPS_UNAVAILABLE`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_fips_unavailable)

An attempt was made to enable or disable FIPS mode, but FIPS mode was
not available.

### `ERR_CRYPTO_HASH_FINALIZED`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_hash_finalized)

[`hash.digest()`](https://nodejs.org/api/crypto.html#crypto_hash_digest_encoding)
was called multiple times. The `hash.digest()` method must be called no
more than one time per instance of a `Hash` object.

### `ERR_CRYPTO_HASH_UPDATE_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_hash_update_failed)

[`hash.update()`](https://nodejs.org/api/crypto.html#crypto_hash_update_data_inputencoding)
failed for any reason. This should rarely, if ever, happen.

### `ERR_CRYPTO_INCOMPATIBLE_KEY`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_incompatible_key)

The given crypto keys are incompatible with the attempted operation.

### `ERR_CRYPTO_INCOMPATIBLE_KEY_OPTIONS`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_incompatible_key_options)

The selected public or private key encoding is incompatible with other
options.

### `ERR_CRYPTO_INVALID_DIGEST`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_invalid_digest)

An invalid [crypto digest
algorithm](https://nodejs.org/api/crypto.html#crypto_crypto_gethashes)
was specified.

### `ERR_CRYPTO_INVALID_KEY_OBJECT_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_invalid_key_object_type)

The given crypto key object's type is invalid for the attempted
operation.

### `ERR_CRYPTO_INVALID_STATE`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_invalid_state)

A crypto method was used on an object that was in an invalid state. For
instance, calling
[`cipher.getAuthTag()`](https://nodejs.org/api/crypto.html#crypto_cipher_getauthtag)
before calling `cipher.final()`.

### `ERR_CRYPTO_PBKDF2_ERROR`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_pbkdf2_error)

The PBKDF2 algorithm failed for unspecified reasons. OpenSSL does not
provide more details and therefore neither does Node.js.

### `ERR_CRYPTO_SCRYPT_INVALID_PARAMETER`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_scrypt_invalid_parameter)

One or more
[`crypto.scrypt()`](https://nodejs.org/api/crypto.html#crypto_crypto_scrypt_password_salt_keylen_options_callback)
or
[`crypto.scryptSync()`](https://nodejs.org/api/crypto.html#crypto_crypto_scryptsync_password_salt_keylen_options)
parameters are outside their legal range.

### `ERR_CRYPTO_SCRYPT_NOT_SUPPORTED`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_scrypt_not_supported)

Node.js was compiled without `scrypt` support. Not possible with the
official release binaries but can happen with custom builds, including
distro builds.

### `ERR_CRYPTO_SIGN_KEY_REQUIRED`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_sign_key_required)

A signing `key` was not provided to the
[`sign.sign()`](https://nodejs.org/api/crypto.html#crypto_sign_sign_privatekey_outputencoding)
method.

### `ERR_CRYPTO_TIMING_SAFE_EQUAL_LENGTH`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_timing_safe_equal_length)

[`crypto.timingSafeEqual()`](https://nodejs.org/api/crypto.html#crypto_crypto_timingsafeequal_a_b)
was called with `Buffer`, `TypedArray`, or `DataView` arguments of
different lengths.

### `ERR_CRYPTO_UNKNOWN_CIPHER`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_unknown_cipher)

An unknown cipher was specified.

### `ERR_CRYPTO_UNKNOWN_DH_GROUP`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_unknown_dh_group)

An unknown Diffie-Hellman group name was given. See
[`crypto.getDiffieHellman()`](https://nodejs.org/api/crypto.html#crypto_crypto_getdiffiehellman_groupname)
for a list of valid group names.

### `ERR_DIR_CLOSED`[\#](https://nodejs.org/api/errors.html#errors_err_dir_closed)

The [`fs.Dir`](https://nodejs.org/api/fs.html#fs_class_fs_dir) was
previously closed.

### `ERR_DIR_CONCURRENT_OPERATION`[\#](https://nodejs.org/api/errors.html#errors_err_dir_concurrent_operation)

Added in: v14.3.0

A synchronous read or close call was attempted on an
[`fs.Dir`](https://nodejs.org/api/fs.html#fs_class_fs_dir) which has
ongoing asynchronous operations.

### `ERR_DNS_SET_SERVERS_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_dns_set_servers_failed)

`c-ares` failed to set the DNS server.

### `ERR_DOMAIN_CALLBACK_NOT_AVAILABLE`[\#](https://nodejs.org/api/errors.html#errors_err_domain_callback_not_available)

The `domain` module was not usable since it could not establish the
required error handling hooks, because
[`process.setUncaughtExceptionCaptureCallback()`](https://nodejs.org/api/process.html#process_process_setuncaughtexceptioncapturecallback_fn)
had been called at an earlier point in time.

### `ERR_DOMAIN_CANNOT_SET_UNCAUGHT_EXCEPTION_CAPTURE`[\#](https://nodejs.org/api/errors.html#errors_err_domain_cannot_set_uncaught_exception_capture)

[`process.setUncaughtExceptionCaptureCallback()`](https://nodejs.org/api/process.html#process_process_setuncaughtexceptioncapturecallback_fn)
could not be called because the `domain` module has been loaded at an
earlier point in time.

The stack trace is extended to include the point in time at which the
`domain` module had been loaded.

### `ERR_ENCODING_INVALID_ENCODED_DATA`[\#](https://nodejs.org/api/errors.html#errors_err_encoding_invalid_encoded_data)

Data provided to `TextDecoder()` API was invalid according to the
encoding provided.

### `ERR_ENCODING_NOT_SUPPORTED`[\#](https://nodejs.org/api/errors.html#errors_err_encoding_not_supported)

Encoding provided to `TextDecoder()` API was not one of the [WHATWG
Supported
Encodings](https://nodejs.org/api/util.html#util_whatwg_supported_encodings).

### `ERR_EVAL_ESM_CANNOT_PRINT`[\#](https://nodejs.org/api/errors.html#errors_err_eval_esm_cannot_print)

`--print` cannot be used with ESM input.

### `ERR_EVENT_RECURSION`[\#](https://nodejs.org/api/errors.html#errors_err_event_recursion)

Thrown when an attempt is made to recursively dispatch an event on
`EventTarget`.

### `ERR_EXECUTION_ENVIRONMENT_NOT_AVAILABLE`[\#](https://nodejs.org/api/errors.html#errors_err_execution_environment_not_available)

The JS execution context is not associated with a Node.js environment.
This may occur when Node.js is used as an embedded library and some
hooks for the JS engine are not set up properly.

### `ERR_FALSY_VALUE_REJECTION`[\#](https://nodejs.org/api/errors.html#errors_err_falsy_value_rejection)

A `Promise` that was callbackified via `util.callbackify()` was rejected
with a falsy value.

#### `ERR_FEATURE_UNAVAILABLE_ON_PLATFORM`[\#](https://nodejs.org/api/errors.html#errors_err_feature_unavailable_on_platform)

Added in: v14.0.0

Used when a feature that is not available to the current platform which
is running Node.js is used.

### `ERR_FS_FILE_TOO_LARGE`[\#](https://nodejs.org/api/errors.html#errors_err_fs_file_too_large)

An attempt has been made to read a file whose size is larger than the
maximum allowed size for a `Buffer`.

### `ERR_FS_INVALID_SYMLINK_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_fs_invalid_symlink_type)

An invalid symlink type was passed to the
[`fs.symlink()`](https://nodejs.org/api/fs.html#fs_fs_symlink_target_path_type_callback)
or
[`fs.symlinkSync()`](https://nodejs.org/api/fs.html#fs_fs_symlinksync_target_path_type)
methods.

### `ERR_HTTP_HEADERS_SENT`[\#](https://nodejs.org/api/errors.html#errors_err_http_headers_sent)

An attempt was made to add more headers after the headers had already
been sent.

### `ERR_HTTP_INVALID_HEADER_VALUE`[\#](https://nodejs.org/api/errors.html#errors_err_http_invalid_header_value)

An invalid HTTP header value was specified.

### `ERR_HTTP_INVALID_STATUS_CODE`[\#](https://nodejs.org/api/errors.html#errors_err_http_invalid_status_code)

Status code was outside the regular status code range (100-999).

### `ERR_HTTP_TRAILER_INVALID`[\#](https://nodejs.org/api/errors.html#errors_err_http_trailer_invalid)

The `Trailer` header was set even though the transfer encoding does not
support that.

### `ERR_HTTP2_ALTSVC_INVALID_ORIGIN`[\#](https://nodejs.org/api/errors.html#errors_err_http2_altsvc_invalid_origin)

HTTP/2 ALTSVC frames require a valid origin.

### `ERR_HTTP2_ALTSVC_LENGTH`[\#](https://nodejs.org/api/errors.html#errors_err_http2_altsvc_length)

HTTP/2 ALTSVC frames are limited to a maximum of 16,382 payload bytes.

### `ERR_HTTP2_CONNECT_AUTHORITY`[\#](https://nodejs.org/api/errors.html#errors_err_http2_connect_authority)

For HTTP/2 requests using the `CONNECT` method, the `:authority`
pseudo-header is required.

### `ERR_HTTP2_CONNECT_PATH`[\#](https://nodejs.org/api/errors.html#errors_err_http2_connect_path)

For HTTP/2 requests using the `CONNECT` method, the `:path`
pseudo-header is forbidden.

### `ERR_HTTP2_CONNECT_SCHEME`[\#](https://nodejs.org/api/errors.html#errors_err_http2_connect_scheme)

For HTTP/2 requests using the `CONNECT` method, the `:scheme`
pseudo-header is forbidden.

### `ERR_HTTP2_ERROR`[\#](https://nodejs.org/api/errors.html#errors_err_http2_error)

A non-specific HTTP/2 error has occurred.

### `ERR_HTTP2_GOAWAY_SESSION`[\#](https://nodejs.org/api/errors.html#errors_err_http2_goaway_session)

New HTTP/2 Streams may not be opened after the `Http2Session` has
received a `GOAWAY` frame from the connected peer.

### `ERR_HTTP2_HEADERS_AFTER_RESPOND`[\#](https://nodejs.org/api/errors.html#errors_err_http2_headers_after_respond)

An additional headers was specified after an HTTP/2 response was
initiated.

### `ERR_HTTP2_HEADERS_SENT`[\#](https://nodejs.org/api/errors.html#errors_err_http2_headers_sent)

An attempt was made to send multiple response headers.

### `ERR_HTTP2_HEADER_SINGLE_VALUE`[\#](https://nodejs.org/api/errors.html#errors_err_http2_header_single_value)

Multiple values were provided for an HTTP/2 header field that was
required to have only a single value.

### `ERR_HTTP2_INFO_STATUS_NOT_ALLOWED`[\#](https://nodejs.org/api/errors.html#errors_err_http2_info_status_not_allowed)

Informational HTTP status codes (`1xx`) may not be set as the response
status code on HTTP/2 responses.

### `ERR_HTTP2_INVALID_CONNECTION_HEADERS`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_connection_headers)

HTTP/1 connection specific headers are forbidden to be used in HTTP/2
requests and responses.

### `ERR_HTTP2_INVALID_HEADER_VALUE`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_header_value)

An invalid HTTP/2 header value was specified.

### `ERR_HTTP2_INVALID_INFO_STATUS`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_info_status)

An invalid HTTP informational status code has been specified.
Informational status codes must be an integer between `100` and `199`
(inclusive).

### `ERR_HTTP2_INVALID_ORIGIN`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_origin)

HTTP/2 `ORIGIN` frames require a valid origin.

### `ERR_HTTP2_INVALID_PACKED_SETTINGS_LENGTH`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_packed_settings_length)

Input `Buffer` and `Uint8Array` instances passed to the
`http2.getUnpackedSettings()` API must have a length that is a multiple
of six.

### `ERR_HTTP2_INVALID_PSEUDOHEADER`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_pseudoheader)

Only valid HTTP/2 pseudoheaders (`:status`, `:path`, `:authority`,
`:scheme`, and `:method`) may be used.

### `ERR_HTTP2_INVALID_SESSION`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_session)

An action was performed on an `Http2Session` object that had already
been destroyed.

### `ERR_HTTP2_INVALID_SETTING_VALUE`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_setting_value)

An invalid value has been specified for an HTTP/2 setting.

### `ERR_HTTP2_INVALID_STREAM`[\#](https://nodejs.org/api/errors.html#errors_err_http2_invalid_stream)

An operation was performed on a stream that had already been destroyed.

### `ERR_HTTP2_MAX_PENDING_SETTINGS_ACK`[\#](https://nodejs.org/api/errors.html#errors_err_http2_max_pending_settings_ack)

Whenever an HTTP/2 `SETTINGS` frame is sent to a connected peer, the
peer is required to send an acknowledgment that it has received and
applied the new `SETTINGS`. By default, a maximum number of
unacknowledged `SETTINGS` frames may be sent at any given time. This
error code is used when that limit has been reached.

### `ERR_HTTP2_NESTED_PUSH`[\#](https://nodejs.org/api/errors.html#errors_err_http2_nested_push)

An attempt was made to initiate a new push stream from within a push
stream. Nested push streams are not permitted.

### `ERR_HTTP2_NO_SOCKET_MANIPULATION`[\#](https://nodejs.org/api/errors.html#errors_err_http2_no_socket_manipulation)

An attempt was made to directly manipulate (read, write, pause, resume,
etc.) a socket attached to an `Http2Session`.

### `ERR_HTTP2_ORIGIN_LENGTH`[\#](https://nodejs.org/api/errors.html#errors_err_http2_origin_length)

HTTP/2 `ORIGIN` frames are limited to a length of 16382 bytes.

### `ERR_HTTP2_OUT_OF_STREAMS`[\#](https://nodejs.org/api/errors.html#errors_err_http2_out_of_streams)

The number of streams created on a single HTTP/2 session reached the
maximum limit.

### `ERR_HTTP2_PAYLOAD_FORBIDDEN`[\#](https://nodejs.org/api/errors.html#errors_err_http2_payload_forbidden)

A message payload was specified for an HTTP response code for which a
payload is forbidden.

### `ERR_HTTP2_PING_CANCEL`[\#](https://nodejs.org/api/errors.html#errors_err_http2_ping_cancel)

An HTTP/2 ping was canceled.

### `ERR_HTTP2_PING_LENGTH`[\#](https://nodejs.org/api/errors.html#errors_err_http2_ping_length)

HTTP/2 ping payloads must be exactly 8 bytes in length.

### `ERR_HTTP2_PSEUDOHEADER_NOT_ALLOWED`[\#](https://nodejs.org/api/errors.html#errors_err_http2_pseudoheader_not_allowed)

An HTTP/2 pseudo-header has been used inappropriately. Pseudo-headers
are header key names that begin with the `:` prefix.

### `ERR_HTTP2_PUSH_DISABLED`[\#](https://nodejs.org/api/errors.html#errors_err_http2_push_disabled)

An attempt was made to create a push stream, which had been disabled by
the client.

### `ERR_HTTP2_SEND_FILE`[\#](https://nodejs.org/api/errors.html#errors_err_http2_send_file)

An attempt was made to use the
`Http2Stream.prototype.responseWithFile()` API to send a directory.

### `ERR_HTTP2_SEND_FILE_NOSEEK`[\#](https://nodejs.org/api/errors.html#errors_err_http2_send_file_noseek)

An attempt was made to use the
`Http2Stream.prototype.responseWithFile()` API to send something other
than a regular file, but `offset` or `length` options were provided.

### `ERR_HTTP2_SESSION_ERROR`[\#](https://nodejs.org/api/errors.html#errors_err_http2_session_error)

The `Http2Session` closed with a non-zero error code.

### `ERR_HTTP2_SETTINGS_CANCEL`[\#](https://nodejs.org/api/errors.html#errors_err_http2_settings_cancel)

The `Http2Session` settings canceled.

### `ERR_HTTP2_SOCKET_BOUND`[\#](https://nodejs.org/api/errors.html#errors_err_http2_socket_bound)

An attempt was made to connect a `Http2Session` object to a `net.Socket`
or `tls.TLSSocket` that had already been bound to another `Http2Session`
object.

### `ERR_HTTP2_SOCKET_UNBOUND`[\#](https://nodejs.org/api/errors.html#errors_err_http2_socket_unbound)

An attempt was made to use the `socket` property of an `Http2Session`
that has already been closed.

### `ERR_HTTP2_STATUS_101`[\#](https://nodejs.org/api/errors.html#errors_err_http2_status_101)

Use of the `101` Informational status code is forbidden in HTTP/2.

### `ERR_HTTP2_STATUS_INVALID`[\#](https://nodejs.org/api/errors.html#errors_err_http2_status_invalid)

An invalid HTTP status code has been specified. Status codes must be an
integer between `100` and `599` (inclusive).

### `ERR_HTTP2_STREAM_CANCEL`[\#](https://nodejs.org/api/errors.html#errors_err_http2_stream_cancel)

An `Http2Stream` was destroyed before any data was transmitted to the
connected peer.

### `ERR_HTTP2_STREAM_ERROR`[\#](https://nodejs.org/api/errors.html#errors_err_http2_stream_error)

A non-zero error code was been specified in an `RST_STREAM` frame.

### `ERR_HTTP2_STREAM_SELF_DEPENDENCY`[\#](https://nodejs.org/api/errors.html#errors_err_http2_stream_self_dependency)

When setting the priority for an HTTP/2 stream, the stream may be marked
as a dependency for a parent stream. This error code is used when an
attempt is made to mark a stream and dependent of itself.

### `ERR_HTTP2_TRAILERS_ALREADY_SENT`[\#](https://nodejs.org/api/errors.html#errors_err_http2_trailers_already_sent)

Trailing headers have already been sent on the `Http2Stream`.

### `ERR_HTTP2_TRAILERS_NOT_READY`[\#](https://nodejs.org/api/errors.html#errors_err_http2_trailers_not_ready)

The `http2stream.sendTrailers()` method cannot be called until after the
`'wantTrailers'` event is emitted on an `Http2Stream` object. The
`'wantTrailers'` event will only be emitted if the `waitForTrailers`
option is set for the `Http2Stream`.

### `ERR_HTTP2_UNSUPPORTED_PROTOCOL`[\#](https://nodejs.org/api/errors.html#errors_err_http2_unsupported_protocol)

`http2.connect()` was passed a URL that uses any protocol other than
`http:` or `https:`.

### `ERR_INTERNAL_ASSERTION`[\#](https://nodejs.org/api/errors.html#errors_err_internal_assertion)

There was a bug in Node.js or incorrect usage of Node.js internals. To
fix the error, open an issue at
[https://github.com/nodejs/node/issues](https://github.com/nodejs/node/issues).

### `ERR_INCOMPATIBLE_OPTION_PAIR`[\#](https://nodejs.org/api/errors.html#errors_err_incompatible_option_pair)

An option pair is incompatible with each other and cannot be used at the
same time.

### `ERR_INPUT_TYPE_NOT_ALLOWED`[\#](https://nodejs.org/api/errors.html#errors_err_input_type_not_allowed)

[Stability:
1](https://nodejs.org/api/documentation.html#documentation_stability_index)
- Experimental

The `--input-type` flag was used to attempt to execute a file. This flag
can only be used with input via `--eval`, `--print` or `STDIN`.

### `ERR_INSPECTOR_ALREADY_ACTIVATED`[\#](https://nodejs.org/api/errors.html#errors_err_inspector_already_activated)

While using the `inspector` module, an attempt was made to activate the
inspector when it already started to listen on a port. Use
`inspector.close()` before activating it on a different address.

### `ERR_INSPECTOR_ALREADY_CONNECTED`[\#](https://nodejs.org/api/errors.html#errors_err_inspector_already_connected)

While using the `inspector` module, an attempt was made to connect when
the inspector was already connected.

### `ERR_INSPECTOR_CLOSED`[\#](https://nodejs.org/api/errors.html#errors_err_inspector_closed)

While using the `inspector` module, an attempt was made to use the
inspector after the session had already closed.

### `ERR_INSPECTOR_COMMAND`[\#](https://nodejs.org/api/errors.html#errors_err_inspector_command)

An error occurred while issuing a command via the `inspector` module.

### `ERR_INSPECTOR_NOT_ACTIVE`[\#](https://nodejs.org/api/errors.html#errors_err_inspector_not_active)

The `inspector` is not active when `inspector.waitForDebugger()` is
called.

### `ERR_INSPECTOR_NOT_AVAILABLE`[\#](https://nodejs.org/api/errors.html#errors_err_inspector_not_available)

The `inspector` module is not available for use.

### `ERR_INSPECTOR_NOT_CONNECTED`[\#](https://nodejs.org/api/errors.html#errors_err_inspector_not_connected)

While using the `inspector` module, an attempt was made to use the
inspector before it was connected.

### `ERR_INSPECTOR_NOT_WORKER`[\#](https://nodejs.org/api/errors.html#errors_err_inspector_not_worker)

An API was called on the main thread that can only be used from the
worker thread.

### `ERR_INVALID_ADDRESS_FAMILY`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_address_family)

The provided address family is not understood by the Node.js API.

### `ERR_INVALID_ARG_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_arg_type)

An argument of the wrong type was passed to a Node.js API.

### `ERR_INVALID_ARG_VALUE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_arg_value)

An invalid or unsupported value was passed for a given argument.

### `ERR_INVALID_ASYNC_ID`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_async_id)

An invalid `asyncId` or `triggerAsyncId` was passed using `AsyncHooks`.
An id less than -1 should never happen.

### `ERR_INVALID_BUFFER_SIZE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_buffer_size)

A swap was performed on a `Buffer` but its size was not compatible with
the operation.

### `ERR_INVALID_CALLBACK`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_callback)

A callback function was required but was not been provided to a Node.js
API.

### `ERR_INVALID_CHAR`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_char)

Invalid characters were detected in headers.

### `ERR_INVALID_CURSOR_POS`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_cursor_pos)

A cursor on a given stream cannot be moved to a specified row without a
specified column.

### `ERR_INVALID_FD`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_fd)

A file descriptor ('fd') was not valid (e.g. it was a negative value).

### `ERR_INVALID_FD_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_fd_type)

A file descriptor ('fd') type was not valid.

### `ERR_INVALID_FILE_URL_HOST`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_file_url_host)

A Node.js API that consumes `file:` URLs (such as certain functions in
the [`fs`](https://nodejs.org/api/fs.html) module) encountered a file
URL with an incompatible host. This situation can only occur on
Unix-like systems where only `localhost` or an empty host is supported.

### `ERR_INVALID_FILE_URL_PATH`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_file_url_path)

A Node.js API that consumes `file:` URLs (such as certain functions in
the [`fs`](https://nodejs.org/api/fs.html) module) encountered a file
URL with an incompatible path. The exact semantics for determining
whether a path can be used is platform-dependent.

### `ERR_INVALID_HANDLE_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_handle_type)

An attempt was made to send an unsupported "handle" over an IPC
communication channel to a child process. See
[`subprocess.send()`](https://nodejs.org/api/child_process.html#child_process_subprocess_send_message_sendhandle_options_callback)
and
[`process.send()`](https://nodejs.org/api/process.html#process_process_send_message_sendhandle_options_callback)
for more information.

### `ERR_INVALID_HTTP_TOKEN`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_http_token)

An invalid HTTP token was supplied.

### `ERR_INVALID_IP_ADDRESS`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_ip_address)

An IP address is not valid.

### `ERR_INVALID_MODULE_SPECIFIER`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_module_specifier)

The imported module string is an invalid URL, package name, or package
subpath specifier.

### `ERR_INVALID_OPT_VALUE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_opt_value)

An invalid or unexpected value was passed in an options object.

### `ERR_INVALID_OPT_VALUE_ENCODING`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_opt_value_encoding)

An invalid or unknown file encoding was passed.

### `ERR_INVALID_PACKAGE_CONFIG`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_package_config)

An invalid `package.json` file was found which failed parsing.

### `ERR_INVALID_PACKAGE_TARGET`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_package_target)

The `package.json`
[exports](https://nodejs.org/api/esm.html#esm_package_entry_points)
field contains an invalid target mapping value for the attempted module
resolution.

### `ERR_INVALID_PERFORMANCE_MARK`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_performance_mark)

While using the Performance Timing API (`perf_hooks`), a performance
mark is invalid.

### `ERR_INVALID_PROTOCOL`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_protocol)

An invalid `options.protocol` was passed to `http.request()`.

### `ERR_INVALID_REPL_EVAL_CONFIG`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_repl_eval_config)

Both `breakEvalOnSigint` and `eval` options were set in the
[`REPL`](https://nodejs.org/api/repl.html) config, which is not
supported.

### `ERR_INVALID_REPL_INPUT`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_repl_input)

The input may not be used in the
[`REPL`](https://nodejs.org/api/repl.html). All prohibited inputs are
documented in the [`REPL`](https://nodejs.org/api/repl.html)'s
documentation.

### `ERR_INVALID_RETURN_PROPERTY`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_return_property)

Thrown in case a function option does not provide a valid value for one
of its returned object properties on execution.

### `ERR_INVALID_RETURN_PROPERTY_VALUE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_return_property_value)

Thrown in case a function option does not provide an expected value type
for one of its returned object properties on execution.

### `ERR_INVALID_RETURN_VALUE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_return_value)

Thrown in case a function option does not return an expected value type
on execution, such as when a function is expected to return a promise.

### `ERR_INVALID_SYNC_FORK_INPUT`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_sync_fork_input)

A `Buffer`, `TypedArray`, `DataView` or `string` was provided as stdio
input to an asynchronous fork. See the documentation for the
[`child_process`](https://nodejs.org/api/child_process.html) module for
more information.

### `ERR_INVALID_THIS`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_this)

A Node.js API function was called with an incompatible `this` value.

    const urlSearchParams = new URLSearchParams('foo=bar&baz=new');

    const buf = Buffer.alloc(1);
    urlSearchParams.has.call(buf, 'foo');
    // Throws a TypeError with code 'ERR_INVALID_THIS'

### `ERR_INVALID_TRANSFER_OBJECT`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_transfer_object)

An invalid transfer object was passed to `postMessage()`.

### `ERR_INVALID_TUPLE`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_tuple)

An element in the `iterable` provided to the
[WHATWG](https://nodejs.org/api/url.html#url_the_whatwg_url_api)
[`URLSearchParams`
constructor](https://nodejs.org/api/url.html#url_new_urlsearchparams_iterable)
did not represent a `[name, value]` tuple – that is, if an element is
not iterable, or does not consist of exactly two elements.

### `ERR_INVALID_URI`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_uri)

An invalid URI was passed.

### `ERR_INVALID_URL`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_url)

An invalid URL was passed to the
[WHATWG](https://nodejs.org/api/url.html#url_the_whatwg_url_api) [`URL`
constructor](https://nodejs.org/api/url.html#url_new_url_input_base) to
be parsed. The thrown error object typically has an additional property
`'input'` that contains the URL that failed to parse.

### `ERR_INVALID_URL_SCHEME`[\#](https://nodejs.org/api/errors.html#errors_err_invalid_url_scheme)

An attempt was made to use a URL of an incompatible scheme (protocol)
for a specific purpose. It is only used in the [WHATWG URL
API](https://nodejs.org/api/url.html#url_the_whatwg_url_api) support in
the [`fs`](https://nodejs.org/api/fs.html) module (which only accepts
URLs with `'file'` scheme), but may be used in other Node.js APIs as
well in the future.

### `ERR_IPC_CHANNEL_CLOSED`[\#](https://nodejs.org/api/errors.html#errors_err_ipc_channel_closed)

An attempt was made to use an IPC communication channel that was already
closed.

### `ERR_IPC_DISCONNECTED`[\#](https://nodejs.org/api/errors.html#errors_err_ipc_disconnected)

An attempt was made to disconnect an IPC communication channel that was
already disconnected. See the documentation for the
[`child_process`](https://nodejs.org/api/child_process.html) module for
more information.

### `ERR_IPC_ONE_PIPE`[\#](https://nodejs.org/api/errors.html#errors_err_ipc_one_pipe)

An attempt was made to create a child Node.js process using more than
one IPC communication channel. See the documentation for the
[`child_process`](https://nodejs.org/api/child_process.html) module for
more information.

### `ERR_IPC_SYNC_FORK`[\#](https://nodejs.org/api/errors.html#errors_err_ipc_sync_fork)

An attempt was made to open an IPC communication channel with a
synchronously forked Node.js process. See the documentation for the
[`child_process`](https://nodejs.org/api/child_process.html) module for
more information.

### `ERR_MANIFEST_ASSERT_INTEGRITY`[\#](https://nodejs.org/api/errors.html#errors_err_manifest_assert_integrity)

An attempt was made to load a resource, but the resource did not match
the integrity defined by the policy manifest. See the documentation for
[policy](https://nodejs.org/api/policy.html) manifests for more
information.

### `ERR_MANIFEST_DEPENDENCY_MISSING`[\#](https://nodejs.org/api/errors.html#errors_err_manifest_dependency_missing)

An attempt was made to load a resource, but the resource was not listed
as a dependency from the location that attempted to load it. See the
documentation for [policy](https://nodejs.org/api/policy.html) manifests
for more information.

### `ERR_MANIFEST_INTEGRITY_MISMATCH`[\#](https://nodejs.org/api/errors.html#errors_err_manifest_integrity_mismatch)

An attempt was made to load a policy manifest, but the manifest had
multiple entries for a resource which did not match each other. Update
the manifest entries to match in order to resolve this error. See the
documentation for [policy](https://nodejs.org/api/policy.html) manifests
for more information.

### `ERR_MANIFEST_INVALID_RESOURCE_FIELD`[\#](https://nodejs.org/api/errors.html#errors_err_manifest_invalid_resource_field)

A policy manifest resource had an invalid value for one of its fields.
Update the manifest entry to match in order to resolve this error. See
the documentation for [policy](https://nodejs.org/api/policy.html)
manifests for more information.

### `ERR_MANIFEST_PARSE_POLICY`[\#](https://nodejs.org/api/errors.html#errors_err_manifest_parse_policy)

An attempt was made to load a policy manifest, but the manifest was
unable to be parsed. See the documentation for
[policy](https://nodejs.org/api/policy.html) manifests for more
information.

### `ERR_MANIFEST_TDZ`[\#](https://nodejs.org/api/errors.html#errors_err_manifest_tdz)

An attempt was made to read from a policy manifest, but the manifest
initialization has not yet taken place. This is likely a bug in Node.js.

### `ERR_MANIFEST_UNKNOWN_ONERROR`[\#](https://nodejs.org/api/errors.html#errors_err_manifest_unknown_onerror)

A policy manifest was loaded, but had an unknown value for its "onerror"
behavior. See the documentation for
[policy](https://nodejs.org/api/policy.html) manifests for more
information.

### `ERR_MEMORY_ALLOCATION_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_memory_allocation_failed)

An attempt was made to allocate memory (usually in the C++ layer) but it
failed.

### `ERR_MESSAGE_TARGET_CONTEXT_UNAVAILABLE`[\#](https://nodejs.org/api/errors.html#errors_err_message_target_context_unavailable)

Added in: v14.5.0

A message posted to a
[`MessagePort`](https://nodejs.org/api/worker_threads.html#worker_threads_class_messageport)
could not be deserialized in the target
[vm](https://nodejs.org/api/vm.html) `Context`. Not all Node.js objects
can be successfully instantiated in any context at this time, and
attempting to transfer them using `postMessage()` can fail on the
receiving side in that case.

### `ERR_METHOD_NOT_IMPLEMENTED`[\#](https://nodejs.org/api/errors.html#errors_err_method_not_implemented)

A method is required but not implemented.

### `ERR_MISSING_ARGS`[\#](https://nodejs.org/api/errors.html#errors_err_missing_args)

A required argument of a Node.js API was not passed. This is only used
for strict compliance with the API specification (which in some cases
may accept `func(undefined)` but not `func()`). In most native Node.js
APIs, `func(undefined)` and `func()` are treated identically, and the
[`ERR_INVALID_ARG_TYPE`](https://nodejs.org/api/errors.html#ERR_INVALID_ARG_TYPE)
error code may be used instead.

### `ERR_MISSING_OPTION`[\#](https://nodejs.org/api/errors.html#errors_err_missing_option)

For APIs that accept options objects, some options might be mandatory.
This code is thrown if a required option is missing.

### `ERR_MISSING_MESSAGE_PORT_IN_TRANSFER_LIST`[\#](https://nodejs.org/api/errors.html#errors_err_missing_message_port_in_transfer_list)

An object that needs to be explicitly listed in the `transferList`
argument was found in the object passed to a `postMessage()` call, but
not provided in the `transferList` for that call. Usually, this is a
`MessagePort`.

### `ERR_MISSING_PASSPHRASE`[\#](https://nodejs.org/api/errors.html#errors_err_missing_passphrase)

An attempt was made to read an encrypted key without specifying a
passphrase.

### `ERR_MISSING_PLATFORM_FOR_WORKER`[\#](https://nodejs.org/api/errors.html#errors_err_missing_platform_for_worker)

The V8 platform used by this instance of Node.js does not support
creating Workers. This is caused by lack of embedder support for
Workers. In particular, this error will not occur with standard builds
of Node.js.

### `ERR_MODULE_NOT_FOUND`[\#](https://nodejs.org/api/errors.html#errors_err_module_not_found)

[Stability:
1](https://nodejs.org/api/documentation.html#documentation_stability_index)
- Experimental

An [ES Module](https://nodejs.org/api/esm.html) could not be resolved.

### `ERR_MULTIPLE_CALLBACK`[\#](https://nodejs.org/api/errors.html#errors_err_multiple_callback)

A callback was called more than once.

A callback is almost always meant to only be called once as the query
can either be fulfilled or rejected but not both at the same time. The
latter would be possible by calling a callback more than once.

### `ERR_NAPI_CONS_FUNCTION`[\#](https://nodejs.org/api/errors.html#errors_err_napi_cons_function)

While using `N-API`, a constructor passed was not a function.

### `ERR_NAPI_INVALID_DATAVIEW_ARGS`[\#](https://nodejs.org/api/errors.html#errors_err_napi_invalid_dataview_args)

While calling `napi_create_dataview()`, a given `offset` was outside the
bounds of the dataview or `offset + length` was larger than a length of
given `buffer`.

### `ERR_NAPI_INVALID_TYPEDARRAY_ALIGNMENT`[\#](https://nodejs.org/api/errors.html#errors_err_napi_invalid_typedarray_alignment)

While calling `napi_create_typedarray()`, the provided `offset` was not
a multiple of the element size.

### `ERR_NAPI_INVALID_TYPEDARRAY_LENGTH`[\#](https://nodejs.org/api/errors.html#errors_err_napi_invalid_typedarray_length)

While calling `napi_create_typedarray()`,
`(length * size_of_element) + byte_offset` was larger than the length of
given `buffer`.

### `ERR_NAPI_TSFN_CALL_JS`[\#](https://nodejs.org/api/errors.html#errors_err_napi_tsfn_call_js)

An error occurred while invoking the JavaScript portion of the
thread-safe function.

### `ERR_NAPI_TSFN_GET_UNDEFINED`[\#](https://nodejs.org/api/errors.html#errors_err_napi_tsfn_get_undefined)

An error occurred while attempting to retrieve the JavaScript
`undefined` value.

### `ERR_NAPI_TSFN_START_IDLE_LOOP`[\#](https://nodejs.org/api/errors.html#errors_err_napi_tsfn_start_idle_loop)

On the main thread, values are removed from the queue associated with
the thread-safe function in an idle loop. This error indicates that an
error has occurred when attempting to start the loop.

### `ERR_NAPI_TSFN_STOP_IDLE_LOOP`[\#](https://nodejs.org/api/errors.html#errors_err_napi_tsfn_stop_idle_loop)

Once no more items are left in the queue, the idle loop must be
suspended. This error indicates that the idle loop has failed to stop.

### `ERR_NO_CRYPTO`[\#](https://nodejs.org/api/errors.html#errors_err_no_crypto)

An attempt was made to use crypto features while Node.js was not
compiled with OpenSSL crypto support.

### `ERR_NO_ICU`[\#](https://nodejs.org/api/errors.html#errors_err_no_icu)

An attempt was made to use features that require
[ICU](https://nodejs.org/api/intl.html#intl_internationalization_support),
but Node.js was not compiled with ICU support.

### `ERR_NON_CONTEXT_AWARE_DISABLED`[\#](https://nodejs.org/api/errors.html#errors_err_non_context_aware_disabled)

A non-context-aware native addon was loaded in a process that disallows
them.

### `ERR_OUT_OF_RANGE`[\#](https://nodejs.org/api/errors.html#errors_err_out_of_range)

A given value is out of the accepted range.

### `ERR_PACKAGE_IMPORT_NOT_DEFINED`[\#](https://nodejs.org/api/errors.html#errors_err_package_import_not_defined)

The `package.json` ["imports"
field](https://nodejs.org/api/esm.html#esm_internal_package_imports)
does not define the given internal package specifier mapping.

### `ERR_PACKAGE_PATH_NOT_EXPORTED`[\#](https://nodejs.org/api/errors.html#errors_err_package_path_not_exported)

The `package.json`
[exports](https://nodejs.org/api/esm.html#esm_package_entry_points)
field does not export the requested subpath. Because exports are
encapsulated, private internal modules that are not exported cannot be
imported through the package resolution, unless using an absolute URL.

### `ERR_PROTO_ACCESS`[\#](https://nodejs.org/api/errors.html#errors_err_proto_access)

Accessing `Object.prototype.__proto__` has been forbidden using
[`--disable-proto=throw`](https://nodejs.org/api/cli.html#cli_disable_proto_mode).
[`Object.getPrototypeOf`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf)
and
[`Object.setPrototypeOf`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/setPrototypeOf)
should be used to get and set the prototype of an object.

### `ERR_REQUIRE_ESM`[\#](https://nodejs.org/api/errors.html#errors_err_require_esm)

[Stability:
1](https://nodejs.org/api/documentation.html#documentation_stability_index)
- Experimental

An attempt was made to `require()` an [ES
Module](https://nodejs.org/api/esm.html).

### `ERR_SCRIPT_EXECUTION_INTERRUPTED`[\#](https://nodejs.org/api/errors.html#errors_err_script_execution_interrupted)

Script execution was interrupted by `SIGINT` (For example, when Ctrl+C
was pressed).

### `ERR_SCRIPT_EXECUTION_TIMEOUT`[\#](https://nodejs.org/api/errors.html#errors_err_script_execution_timeout)

Script execution timed out, possibly due to bugs in the script being
executed.

### `ERR_SERVER_ALREADY_LISTEN`[\#](https://nodejs.org/api/errors.html#errors_err_server_already_listen)

The
[`server.listen()`](https://nodejs.org/api/net.html#net_server_listen)
method was called while a `net.Server` was already listening. This
applies to all instances of `net.Server`, including HTTP, HTTPS, and
HTTP/2 `Server` instances.

### `ERR_SERVER_NOT_RUNNING`[\#](https://nodejs.org/api/errors.html#errors_err_server_not_running)

The
[`server.close()`](https://nodejs.org/api/net.html#net_server_close_callback)
method was called when a `net.Server` was not running. This applies to
all instances of `net.Server`, including HTTP, HTTPS, and HTTP/2
`Server` instances.

### `ERR_SOCKET_ALREADY_BOUND`[\#](https://nodejs.org/api/errors.html#errors_err_socket_already_bound)

An attempt was made to bind a socket that has already been bound.

### `ERR_SOCKET_BAD_BUFFER_SIZE`[\#](https://nodejs.org/api/errors.html#errors_err_socket_bad_buffer_size)

An invalid (negative) size was passed for either the `recvBufferSize` or
`sendBufferSize` options in
[`dgram.createSocket()`](https://nodejs.org/api/dgram.html#dgram_dgram_createsocket_options_callback).

### `ERR_SOCKET_BAD_PORT`[\#](https://nodejs.org/api/errors.html#errors_err_socket_bad_port)

An API function expecting a port \>= 0 and \< 65536 received an invalid
value.

### `ERR_SOCKET_BAD_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_socket_bad_type)

An API function expecting a socket type (`udp4` or `udp6`) received an
invalid value.

### `ERR_SOCKET_BUFFER_SIZE`[\#](https://nodejs.org/api/errors.html#errors_err_socket_buffer_size)

While using
[`dgram.createSocket()`](https://nodejs.org/api/dgram.html#dgram_dgram_createsocket_options_callback),
the size of the receive or send `Buffer` could not be determined.

### `ERR_SOCKET_CLOSED`[\#](https://nodejs.org/api/errors.html#errors_err_socket_closed)

An attempt was made to operate on an already closed socket.

### `ERR_SOCKET_DGRAM_IS_CONNECTED`[\#](https://nodejs.org/api/errors.html#errors_err_socket_dgram_is_connected)

A
[`dgram.connect()`](https://nodejs.org/api/dgram.html#dgram_socket_connect_port_address_callback)
call was made on an already connected socket.

### `ERR_SOCKET_DGRAM_NOT_CONNECTED`[\#](https://nodejs.org/api/errors.html#errors_err_socket_dgram_not_connected)

A
[`dgram.disconnect()`](https://nodejs.org/api/dgram.html#dgram_socket_disconnect)
or
[`dgram.remoteAddress()`](https://nodejs.org/api/dgram.html#dgram_socket_remoteaddress)
call was made on a disconnected socket.

### `ERR_SOCKET_DGRAM_NOT_RUNNING`[\#](https://nodejs.org/api/errors.html#errors_err_socket_dgram_not_running)

A call was made and the UDP subsystem was not running.

### `ERR_SRI_PARSE`[\#](https://nodejs.org/api/errors.html#errors_err_sri_parse)

A string was provided for a Subresource Integrity check, but was unable
to be parsed. Check the format of integrity attributes by looking at the
[Subresource Integrity
specification](https://www.w3.org/TR/SRI/#the-integrity-attribute).

### `ERR_STREAM_CANNOT_PIPE`[\#](https://nodejs.org/api/errors.html#errors_err_stream_cannot_pipe)

An attempt was made to call
[`stream.pipe()`](https://nodejs.org/api/stream.html#stream_readable_pipe_destination_options)
on a
[`Writable`](https://nodejs.org/api/stream.html#stream_class_stream_writable)
stream.

### `ERR_STREAM_DESTROYED`[\#](https://nodejs.org/api/errors.html#errors_err_stream_destroyed)

A stream method was called that cannot complete because the stream was
destroyed using `stream.destroy()`.

### `ERR_STREAM_ALREADY_FINISHED`[\#](https://nodejs.org/api/errors.html#errors_err_stream_already_finished)

A stream method was called that cannot complete because the stream was
finished.

### `ERR_STREAM_NULL_VALUES`[\#](https://nodejs.org/api/errors.html#errors_err_stream_null_values)

An attempt was made to call
[`stream.write()`](https://nodejs.org/api/stream.html#stream_writable_write_chunk_encoding_callback)
with a `null` chunk.

### `ERR_STREAM_PREMATURE_CLOSE`[\#](https://nodejs.org/api/errors.html#errors_err_stream_premature_close)

An error returned by `stream.finished()` and `stream.pipeline()`, when a
stream or a pipeline ends non gracefully with no explicit error.

### `ERR_STREAM_PUSH_AFTER_EOF`[\#](https://nodejs.org/api/errors.html#errors_err_stream_push_after_eof)

An attempt was made to call
[`stream.push()`](https://nodejs.org/api/stream.html#stream_readable_push_chunk_encoding)
after a `null`(EOF) had been pushed to the stream.

### `ERR_STREAM_UNSHIFT_AFTER_END_EVENT`[\#](https://nodejs.org/api/errors.html#errors_err_stream_unshift_after_end_event)

An attempt was made to call
[`stream.unshift()`](https://nodejs.org/api/stream.html#stream_readable_unshift_chunk_encoding)
after the `'end'` event was emitted.

### `ERR_STREAM_WRAP`[\#](https://nodejs.org/api/errors.html#errors_err_stream_wrap)

Prevents an abort if a string decoder was set on the Socket or if the
decoder is in `objectMode`.

    const Socket = require('net').Socket;
    const instance = new Socket();

    instance.setEncoding('utf8');

### `ERR_STREAM_WRITE_AFTER_END`[\#](https://nodejs.org/api/errors.html#errors_err_stream_write_after_end)

An attempt was made to call
[`stream.write()`](https://nodejs.org/api/stream.html#stream_writable_write_chunk_encoding_callback)
after `stream.end()` has been called.

### `ERR_STRING_TOO_LONG`[\#](https://nodejs.org/api/errors.html#errors_err_string_too_long)

An attempt has been made to create a string longer than the maximum
allowed length.

### `ERR_SYNTHETIC`[\#](https://nodejs.org/api/errors.html#errors_err_synthetic)

An artificial error object used to capture the call stack for diagnostic
reports.

### `ERR_SYSTEM_ERROR`[\#](https://nodejs.org/api/errors.html#errors_err_system_error)

An unspecified or non-specific system error has occurred within the
Node.js process. The error object will have an `err.info` object
property with additional details.

### `ERR_TLS_CERT_ALTNAME_INVALID`[\#](https://nodejs.org/api/errors.html#errors_err_tls_cert_altname_invalid)

While using TLS, the host name/IP of the peer did not match any of the
`subjectAltNames` in its certificate.

### `ERR_TLS_DH_PARAM_SIZE`[\#](https://nodejs.org/api/errors.html#errors_err_tls_dh_param_size)

While using TLS, the parameter offered for the Diffie-Hellman (`DH`)
key-agreement protocol is too small. By default, the key length must be
greater than or equal to 1024 bits to avoid vulnerabilities, even though
it is strongly recommended to use 2048 bits or larger for stronger
security.

### `ERR_TLS_HANDSHAKE_TIMEOUT`[\#](https://nodejs.org/api/errors.html#errors_err_tls_handshake_timeout)

A TLS/SSL handshake timed out. In this case, the server must also abort
the connection.

### `ERR_TLS_INVALID_CONTEXT`[\#](https://nodejs.org/api/errors.html#errors_err_tls_invalid_context)

Added in: v13.3.0

The context must be a `SecureContext`.

### `ERR_TLS_INVALID_STATE`[\#](https://nodejs.org/api/errors.html#errors_err_tls_invalid_state)

Added in: v13.10.0

The TLS socket must be connected and securily established. Ensure the
'secure' event is emitted before continuing.

### `ERR_TLS_INVALID_PROTOCOL_METHOD`[\#](https://nodejs.org/api/errors.html#errors_err_tls_invalid_protocol_method)

The specified `secureProtocol` method is invalid. It is either unknown,
or disabled because it is insecure.

### `ERR_TLS_INVALID_PROTOCOL_VERSION`[\#](https://nodejs.org/api/errors.html#errors_err_tls_invalid_protocol_version)

Valid TLS protocol versions are `'TLSv1'`, `'TLSv1.1'`, or `'TLSv1.2'`.

### `ERR_TLS_PROTOCOL_VERSION_CONFLICT`[\#](https://nodejs.org/api/errors.html#errors_err_tls_protocol_version_conflict)

Attempting to set a TLS protocol `minVersion` or `maxVersion` conflicts
with an attempt to set the `secureProtocol` explicitly. Use one
mechanism or the other.

### `ERR_TLS_RENEGOTIATION_DISABLED`[\#](https://nodejs.org/api/errors.html#errors_err_tls_renegotiation_disabled)

An attempt was made to renegotiate TLS on a socket instance with TLS
disabled.

### `ERR_TLS_REQUIRED_SERVER_NAME`[\#](https://nodejs.org/api/errors.html#errors_err_tls_required_server_name)

While using TLS, the `server.addContext()` method was called without
providing a host name in the first parameter.

### `ERR_TLS_SESSION_ATTACK`[\#](https://nodejs.org/api/errors.html#errors_err_tls_session_attack)

An excessive amount of TLS renegotiations is detected, which is a
potential vector for denial-of-service attacks.

### `ERR_TLS_SNI_FROM_SERVER`[\#](https://nodejs.org/api/errors.html#errors_err_tls_sni_from_server)

An attempt was made to issue Server Name Indication from a TLS
server-side socket, which is only valid from a client.

### `ERR_TLS_PSK_SET_IDENTIY_HINT_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_tls_psk_set_identiy_hint_failed)

Failed to set PSK identity hint. Hint may be too long.

### `ERR_TRACE_EVENTS_CATEGORY_REQUIRED`[\#](https://nodejs.org/api/errors.html#errors_err_trace_events_category_required)

The `trace_events.createTracing()` method requires at least one trace
event category.

### `ERR_TRACE_EVENTS_UNAVAILABLE`[\#](https://nodejs.org/api/errors.html#errors_err_trace_events_unavailable)

The `trace_events` module could not be loaded because Node.js was
compiled with the `--without-v8-platform` flag.

### `ERR_TRANSFORM_ALREADY_TRANSFORMING`[\#](https://nodejs.org/api/errors.html#errors_err_transform_already_transforming)

A `Transform` stream finished while it was still transforming.

### `ERR_TRANSFORM_WITH_LENGTH_0`[\#](https://nodejs.org/api/errors.html#errors_err_transform_with_length_0)

A `Transform` stream finished with data still in the write buffer.

### `ERR_TTY_INIT_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_tty_init_failed)

The initialization of a TTY failed due to a system error.

### `ERR_UNAVAILABLE_DURING_EXIT`[\#](https://nodejs.org/api/errors.html#errors_err_unavailable_during_exit)

Function was called within a
[`process.on('exit')`](https://nodejs.org/api/process.html#Event:-%60'exit'%60)
handler that shouldn't be called within
[`process.on('exit')`](https://nodejs.org/api/process.html#Event:-%60'exit'%60)
handler.

### `ERR_UNCAUGHT_EXCEPTION_CAPTURE_ALREADY_SET`[\#](https://nodejs.org/api/errors.html#errors_err_uncaught_exception_capture_already_set)

[`process.setUncaughtExceptionCaptureCallback()`](https://nodejs.org/api/process.html#process_process_setuncaughtexceptioncapturecallback_fn)
was called twice, without first resetting the callback to `null`.

This error is designed to prevent accidentally overwriting a callback
registered from another module.

### `ERR_UNESCAPED_CHARACTERS`[\#](https://nodejs.org/api/errors.html#errors_err_unescaped_characters)

A string that contained unescaped characters was received.

### `ERR_UNHANDLED_ERROR`[\#](https://nodejs.org/api/errors.html#errors_err_unhandled_error)

An unhandled error occurred (for instance, when an `'error'` event is
emitted by an
[`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)
but an `'error'` handler is not registered).

### `ERR_UNKNOWN_BUILTIN_MODULE`[\#](https://nodejs.org/api/errors.html#errors_err_unknown_builtin_module)

Used to identify a specific kind of internal Node.js error that should
not typically be triggered by user code. Instances of this error point
to an internal bug within the Node.js binary itself.

### `ERR_UNKNOWN_CREDENTIAL`[\#](https://nodejs.org/api/errors.html#errors_err_unknown_credential)

A Unix group or user identifier that does not exist was passed.

### `ERR_UNKNOWN_ENCODING`[\#](https://nodejs.org/api/errors.html#errors_err_unknown_encoding)

An invalid or unknown encoding option was passed to an API.

### `ERR_UNKNOWN_FILE_EXTENSION`[\#](https://nodejs.org/api/errors.html#errors_err_unknown_file_extension)

[Stability:
1](https://nodejs.org/api/documentation.html#documentation_stability_index)
- Experimental

An attempt was made to load a module with an unknown or unsupported file
extension.

### `ERR_UNKNOWN_MODULE_FORMAT`[\#](https://nodejs.org/api/errors.html#errors_err_unknown_module_format)

[Stability:
1](https://nodejs.org/api/documentation.html#documentation_stability_index)
- Experimental

An attempt was made to load a module with an unknown or unsupported
format.

### `ERR_UNKNOWN_SIGNAL`[\#](https://nodejs.org/api/errors.html#errors_err_unknown_signal)

An invalid or unknown process signal was passed to an API expecting a
valid signal (such as
[`subprocess.kill()`](https://nodejs.org/api/child_process.html#child_process_subprocess_kill_signal)).

### `ERR_UNSUPPORTED_DIR_IMPORT`[\#](https://nodejs.org/api/errors.html#errors_err_unsupported_dir_import)

`import` a directory URL is unsupported. Instead, [self-reference a
package using its
name](https://nodejs.org/api/esm.html#esm_self_referencing_a_package_using_its_name)
and [define a custom
subpath](https://nodejs.org/api/esm.html#esm_subpath_exports) in the
`"exports"` field of the `package.json` file.

    import './'; // unsupported
    import './index.js'; // supported
    import 'package-name'; // supported

### `ERR_UNSUPPORTED_ESM_URL_SCHEME`[\#](https://nodejs.org/api/errors.html#errors_err_unsupported_esm_url_scheme)

`import` with URL schemes other than `file` and `data` is unsupported.

### `ERR_VALID_PERFORMANCE_ENTRY_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_valid_performance_entry_type)

While using the Performance Timing API (`perf_hooks`), no valid
performance entry types were found.

### `ERR_VM_DYNAMIC_IMPORT_CALLBACK_MISSING`[\#](https://nodejs.org/api/errors.html#errors_err_vm_dynamic_import_callback_missing)

A dynamic import callback was not specified.

### `ERR_VM_MODULE_ALREADY_LINKED`[\#](https://nodejs.org/api/errors.html#errors_err_vm_module_already_linked)

The module attempted to be linked is not eligible for linking, because
of one of the following reasons:

-   It has already been linked (`linkingStatus` is `'linked'`)
-   It is being linked (`linkingStatus` is `'linking'`)
-   Linking has failed for this module (`linkingStatus` is `'errored'`)

### `ERR_VM_MODULE_CACHED_DATA_REJECTED`[\#](https://nodejs.org/api/errors.html#errors_err_vm_module_cached_data_rejected)

The `cachedData` option passed to a module constructor is invalid.

### `ERR_VM_MODULE_CANNOT_CREATE_CACHED_DATA`[\#](https://nodejs.org/api/errors.html#errors_err_vm_module_cannot_create_cached_data)

Cached data cannot be created for modules which have already been
evaluated.

### `ERR_VM_MODULE_DIFFERENT_CONTEXT`[\#](https://nodejs.org/api/errors.html#errors_err_vm_module_different_context)

The module being returned from the linker function is from a different
context than the parent module. Linked modules must share the same
context.

### `ERR_VM_MODULE_LINKING_ERRORED`[\#](https://nodejs.org/api/errors.html#errors_err_vm_module_linking_errored)

The linker function returned a module for which linking has failed.

### `ERR_VM_MODULE_NOT_MODULE`[\#](https://nodejs.org/api/errors.html#errors_err_vm_module_not_module)

The fulfilled value of a linking promise is not a `vm.Module` object.

### `ERR_VM_MODULE_STATUS`[\#](https://nodejs.org/api/errors.html#errors_err_vm_module_status)

The current module's status does not allow for this operation. The
specific meaning of the error depends on the specific function.

### `ERR_WASI_ALREADY_STARTED`[\#](https://nodejs.org/api/errors.html#errors_err_wasi_already_started)

The WASI instance has already started.

### `ERR_WASI_NOT_STARTED`[\#](https://nodejs.org/api/errors.html#errors_err_wasi_not_started)

The WASI instance has not been started.

### `ERR_WORKER_INIT_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_worker_init_failed)

The `Worker` initialization failed.

### `ERR_WORKER_INVALID_EXEC_ARGV`[\#](https://nodejs.org/api/errors.html#errors_err_worker_invalid_exec_argv)

The `execArgv` option passed to the `Worker` constructor contains
invalid flags.

### `ERR_WORKER_NOT_RUNNING`[\#](https://nodejs.org/api/errors.html#errors_err_worker_not_running)

An operation failed because the `Worker` instance is not currently
running.

### `ERR_WORKER_OUT_OF_MEMORY`[\#](https://nodejs.org/api/errors.html#errors_err_worker_out_of_memory)

The `Worker` instance terminated because it reached its memory limit.

### `ERR_WORKER_PATH`[\#](https://nodejs.org/api/errors.html#errors_err_worker_path)

The path for the main script of a worker is neither an absolute path nor
a relative path starting with `./` or `../`.

### `ERR_WORKER_UNSERIALIZABLE_ERROR`[\#](https://nodejs.org/api/errors.html#errors_err_worker_unserializable_error)

All attempts at serializing an uncaught exception from a worker thread
failed.

### `ERR_WORKER_UNSUPPORTED_EXTENSION`[\#](https://nodejs.org/api/errors.html#errors_err_worker_unsupported_extension)

The pathname used for the main script of a worker has an unknown file
extension.

### `ERR_WORKER_UNSUPPORTED_OPERATION`[\#](https://nodejs.org/api/errors.html#errors_err_worker_unsupported_operation)

The requested functionality is not supported in worker threads.

### `ERR_ZLIB_INITIALIZATION_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_zlib_initialization_failed)

Creation of a [`zlib`](https://nodejs.org/api/zlib.html) object failed
due to incorrect configuration.

### `HPE_HEADER_OVERFLOW`[\#](https://nodejs.org/api/errors.html#errors_hpe_header_overflow)

History

Version

Changes

v11.4.0, v10.15.0

Max header size in `http_parser` was set to 8KB.

Too much HTTP header data was received. In order to protect against
malicious or malconfigured clients, if more than 8KB of HTTP header data
is received then HTTP parsing will abort without a request or response
object being created, and an `Error` with this code will be emitted.

### `HPE_UNEXPECTED_CONTENT_LENGTH`[\#](https://nodejs.org/api/errors.html#errors_hpe_unexpected_content_length)

Server is sending both a `Content-Length` header and
`Transfer-Encoding: chunked`.

`Transfer-Encoding: chunked` allows the server to maintain an HTTP
persistent connection for dynamically generated content. In this case,
the `Content-Length` HTTP header cannot be used.

Use `Content-Length` or `Transfer-Encoding: chunked`.

### `MODULE_NOT_FOUND`[\#](https://nodejs.org/api/errors.html#errors_module_not_found)

History

Version

Changes

v12.0.0

Added `requireStack` property.

A module file could not be resolved while attempting a
[`require()`](https://nodejs.org/api/modules.html#modules_require_id) or
`import` operation.

Legacy Node.js error codes[\#](https://nodejs.org/api/errors.html#errors_legacy_node_js_error_codes)
----------------------------------------------------------------------------------------------------

[Stability:
0](https://nodejs.org/api/documentation.html#documentation_stability_index)
- Deprecated. These error codes are either inconsistent, or have been
removed.

### `ERR_CANNOT_TRANSFER_OBJECT`[\#](https://nodejs.org/api/errors.html#errors_err_cannot_transfer_object)

The value passed to `postMessage()` contained an object that is not
supported for transferring.

### `ERR_CLOSED_MESSAGE_PORT`[\#](https://nodejs.org/api/errors.html#errors_err_closed_message_port)

Added in: v10.5.0Removed in: v11.12.0

There was an attempt to use a `MessagePort` instance in a closed state,
usually after `.close()` has been called.

### `ERR_CRYPTO_HASH_DIGEST_NO_UTF16`[\#](https://nodejs.org/api/errors.html#errors_err_crypto_hash_digest_no_utf16)

Added in: v9.0.0Removed in: v12.12.0

The UTF-16 encoding was used with
[`hash.digest()`](https://nodejs.org/api/crypto.html#crypto_hash_digest_encoding).
While the `hash.digest()` method does allow an `encoding` argument to be
passed in, causing the method to return a string rather than a `Buffer`,
the UTF-16 encoding (e.g. `ucs` or `utf16le`) is not supported.

### `ERR_HTTP2_FRAME_ERROR`[\#](https://nodejs.org/api/errors.html#errors_err_http2_frame_error)

Added in: v9.0.0Removed in: v10.0.0

Used when a failure occurs sending an individual frame on the HTTP/2
session.

### `ERR_HTTP2_HEADERS_OBJECT`[\#](https://nodejs.org/api/errors.html#errors_err_http2_headers_object)

Added in: v9.0.0Removed in: v10.0.0

Used when an HTTP/2 Headers Object is expected.

### `ERR_HTTP2_HEADER_REQUIRED`[\#](https://nodejs.org/api/errors.html#errors_err_http2_header_required)

Added in: v9.0.0Removed in: v10.0.0

Used when a required header is missing in an HTTP/2 message.

### `ERR_HTTP2_INFO_HEADERS_AFTER_RESPOND`[\#](https://nodejs.org/api/errors.html#errors_err_http2_info_headers_after_respond)

Added in: v9.0.0Removed in: v10.0.0

HTTP/2 informational headers must only be sent *prior* to calling the
`Http2Stream.prototype.respond()` method.

### `ERR_HTTP2_STREAM_CLOSED`[\#](https://nodejs.org/api/errors.html#errors_err_http2_stream_closed)

Added in: v9.0.0Removed in: v10.0.0

Used when an action has been performed on an HTTP/2 Stream that has
already been closed.

### `ERR_HTTP_INVALID_CHAR`[\#](https://nodejs.org/api/errors.html#errors_err_http_invalid_char)

Added in: v9.0.0Removed in: v10.0.0

Used when an invalid character is found in an HTTP response status
message (reason phrase).

### `ERR_INDEX_OUT_OF_RANGE`[\#](https://nodejs.org/api/errors.html#errors_err_index_out_of_range)

Added in: v10.0.0Removed in: v11.0.0

A given index was out of the accepted range (e.g. negative offsets).

### `ERR_NAPI_CONS_PROTOTYPE_OBJECT`[\#](https://nodejs.org/api/errors.html#errors_err_napi_cons_prototype_object)

Added in: v9.0.0Removed in: v10.0.0

Used by the `N-API` when `Constructor.prototype` is not an object.

### `ERR_NO_LONGER_SUPPORTED`[\#](https://nodejs.org/api/errors.html#errors_err_no_longer_supported)

A Node.js API was called in an unsupported manner, such as
`Buffer.write(string, encoding, offset[, length])`.

### `ERR_OUTOFMEMORY`[\#](https://nodejs.org/api/errors.html#errors_err_outofmemory)

Added in: v9.0.0Removed in: v10.0.0

Used generically to identify that an operation caused an out of memory
condition.

### `ERR_PARSE_HISTORY_DATA`[\#](https://nodejs.org/api/errors.html#errors_err_parse_history_data)

Added in: v9.0.0Removed in: v10.0.0

The `repl` module was unable to parse data from the REPL history file.

### `ERR_SOCKET_CANNOT_SEND`[\#](https://nodejs.org/api/errors.html#errors_err_socket_cannot_send)

Added in: v9.0.0Removed in: v14.0.0

Data could not be sent on a socket.

### `ERR_STDERR_CLOSE`[\#](https://nodejs.org/api/errors.html#errors_err_stderr_close)

History

Version

Changes

v10.12.0

Rather than emitting an error, `process.stderr.end()` now only closes
the stream side but not the underlying resource, making this error
obsolete.

v10.12.0

Removed in: v10.12.0

An attempt was made to close the `process.stderr` stream. By design,
Node.js does not allow `stdout` or `stderr` streams to be closed by user
code.

### `ERR_STDOUT_CLOSE`[\#](https://nodejs.org/api/errors.html#errors_err_stdout_close)

History

Version

Changes

v10.12.0

Rather than emitting an error, `process.stderr.end()` now only closes
the stream side but not the underlying resource, making this error
obsolete.

v10.12.0

Removed in: v10.12.0

An attempt was made to close the `process.stdout` stream. By design,
Node.js does not allow `stdout` or `stderr` streams to be closed by user
code.

### `ERR_STREAM_READ_NOT_IMPLEMENTED`[\#](https://nodejs.org/api/errors.html#errors_err_stream_read_not_implemented)

Added in: v9.0.0Removed in: v10.0.0

Used when an attempt is made to use a readable stream that has not
implemented
[`readable._read()`](https://nodejs.org/api/stream.html#stream_readable_read_size_1).

### `ERR_TLS_RENEGOTIATION_FAILED`[\#](https://nodejs.org/api/errors.html#errors_err_tls_renegotiation_failed)

Added in: v9.0.0Removed in: v10.0.0

Used when a TLS renegotiation request has failed in a non-specific way.

### `ERR_TRANSFERRING_EXTERNALIZED_SHAREDARRAYBUFFER`[\#](https://nodejs.org/api/errors.html#errors_err_transferring_externalized_sharedarraybuffer)

Added in: v10.5.0Removed in: v14.0.0

A `SharedArrayBuffer` whose memory is not managed by the JavaScript
engine or by Node.js was encountered during serialization. Such a
`SharedArrayBuffer` cannot be serialized.

This can only happen when native addons create `SharedArrayBuffer`s in
"externalized" mode, or put existing `SharedArrayBuffer` into
externalized mode.

### `ERR_UNKNOWN_STDIN_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_unknown_stdin_type)

Added in: v8.0.0Removed in: v11.7.0

An attempt was made to launch a Node.js process with an unknown `stdin`
file type. This error is usually an indication of a bug within Node.js
itself, although it is possible for user code to trigger it.

### `ERR_UNKNOWN_STREAM_TYPE`[\#](https://nodejs.org/api/errors.html#errors_err_unknown_stream_type)

Added in: v8.0.0Removed in: v11.7.0

An attempt was made to launch a Node.js process with an unknown `stdout`
or `stderr` file type. This error is usually an indication of a bug
within Node.js itself, although it is possible for user code to trigger
it.

### `ERR_V8BREAKITERATOR`[\#](https://nodejs.org/api/errors.html#errors_err_v8breakiterator)

The V8 `BreakIterator` API was used but the full ICU data set is not
installed.

### `ERR_VALUE_OUT_OF_RANGE`[\#](https://nodejs.org/api/errors.html#errors_err_value_out_of_range)

Added in: v9.0.0Removed in: v10.0.0

Used when a given value is out of the accepted range.

### `ERR_VM_MODULE_NOT_LINKED`[\#](https://nodejs.org/api/errors.html#errors_err_vm_module_not_linked)

The module must be successfully linked before instantiation.

### `ERR_ZLIB_BINDING_CLOSED`[\#](https://nodejs.org/api/errors.html#errors_err_zlib_binding_closed)

Added in: v9.0.0Removed in: v10.0.0

Used when an attempt is made to use a `zlib` object after it has already
been closed.

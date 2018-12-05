# graylog2

[![Build Status](https://travis-ci.com/iroquoisorg/ansible-role-graylog2.svg?branch=master)](https://travis-ci.com/iroquoisorg/ansible-role-memcached)

Ansible role for graylog2

This role was prepared and tested for Ubuntu 16.04.

# Installation

`$ ansible-galaxy install iroquoisorg.graylog2`

# Default settings

```

# Requirements
graylog_java_ppa:                  'ppa:webupd8team/java'
graylog_java_repo:                 'deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main'
graylog_java_src_repo:             'deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main'
graylog_java_repo_keyserver:       'keyserver.ubuntu.com'
graylog_java_repo_key:             'EEA14886'
graylog_version:                   '2.1'
#graylog_apt_deb_url:               "http://packages.graylog2.org/repo/debian/pool/stable/{{ graylog_version }}/g/graylog-{{ graylog_version }}-repository/graylog-{{ graylog_version }}-repository_1-1_all.deb"
graylog_apt_deb_url:               "https://packages.graylog2.org/repo/packages/graylog-{{ graylog_version }}-repository_latest.deb"
graylog_yum_rpm_url:               "https://packages.graylog2.org/repo/packages/graylog-{{ graylog_version }}-repository_latest.rpm"
graylog_java_oracle_installer_key: 'oracle-java8-installer'
graylog_java_oracle_license_key:   'accepted-oracle-license-v1-1'

# General
graylog_is_master:            'True'
graylog_node_id_file:         '/etc/graylog/server/node-id'
graylog_password_secret:      '2jueVqZpwLLjaWxV'
graylog_root_username:        'admin'
graylog_root_password_sha2:   '8c6976e5b5410415bde908bd4dee15dfb167a9c873fc4bb8a81f6f2ab448a918'
graylog_plugin_dir:           '/usr/share/graylog-server/plugin'
graylog_root_email:           ''
graylog_root_timezone:        'UTC'
graylog_alert_check_interval: 60
graylog_disable_sigar:        'False'

# REST
graylog_rest_listen_uri:                   'http://0.0.0.0:9000/api/'
graylog_rest_transport_uri:                ''
graylog_rest_enable_cors:                  'True'
graylog_rest_enable_gzip:                  'True'
graylog_rest_enable_tls:                   'False'
graylog_rest_tls_cert_file:                '/path/to/graylog.crt'
graylog_rest_tls_key_file:                 '/path/to/graylog.key'
graylog_rest_tls_key_password:             'secret'
graylog_rest_max_header_size:              8192
graylog_rest_max_initial_line_length:      4096
graylog_rest_thread_pool_size:             16

# Search
graylog_elasticsearch_template_name:                    'graylog-internal'
graylog_allow_leading_wildcard_searches:                'False'
graylog_allow_highlighting:                             'False'
graylog_elasticsearch_config_file:                      ''
graylog_elasticsearch_shards:                           4
graylog_elasticsearch_replicas:                         0
graylog_elasticsearch_index_prefix:                     'graylog'
graylog_elasticsearch_cluster_name:                     'graylog'
graylog_elasticsearch_node_name_prefix:                 'graylog-'
graylog_elasticsearch_transport_tcp_port:               9350
graylog_elasticsearch_discovery_zen_ping_unicast_hosts: '127.0.0.1:9300'
graylog_elasticsearch_hosts:                            'http://127.0.0.1:9200'
graylog_elasticsearch_network_host:                     ''
graylog_elasticsearch_network_bind_host:                ''
graylog_elasticsearch_network_publish_host:             ''
graylog_elasticsearch_analyzer:                         'standard'
graylog_elasticsearch_output_batch_size:                25
graylog_elasticsearch_output_flush_interval:            1
graylog_elasticsearch_disable_version_check:            'True'
graylog_elasticsearch_http_enabled:                     'False'
graylog_disable_index_optimization:                     'True'
graylog_index_optimization_max_num_segments:            1
graylog_elasticsearch_max_retries:                      2
graylog_elasticsearch_discovery_enabled:                'False'
graylog_elasticsearch_discovery_filter:                 ''
graylog_elasticsearch_discovery_frequency:              '30s'
graylog_elasticsearch_max_total_connections:            20
graylog_elasticsearch_max_total_connections_per_route:  2

# Retention
graylog_no_retention:                        'False'
graylog_elasticsearch_retention_strategy:    'delete'
graylog_rotation_strategy:                   'count'
graylog_elasticsearch_max_docs_per_index:    20000000
graylog_elasticsearch_max_number_of_indices: 20
graylog_elasticsearch_max_size_per_index:    1073741824
graylog_elasticsearch_max_time_per_index:    '1d'

# Processing
graylog_processbuffer_processors:         5
graylog_outputbuffer_processors:          3
graylog_processor_wait_strategy:          'blocking'
graylog_dead_letters_enabled:             'False'
graylog_lb_recognition_period_seconds:    3
graylog_lb_throttle_threshold_percentage: 95
graylog_stream_processing_max_faults:     3
graylog_message_journal_enabled:          'True'
graylog_message_journal_dir:              '/var/lib/graylog-server/journal'
graylog_message_journal_max_age:          '12h'
graylog_message_journal_max_size:         '5gb'
graylog_message_journal_flush_age:        '1m'
graylog_message_journal_flush_interval:   1000000
graylog_message_journal_segment_age:      '1h'
graylog_message_journal_segment_size:     '100mb'
graylog_output_fault_count_threshold:     5
graylog_output_fault_penalty_seconds:     30
graylog_async_eventbus_processors:        2

# Timeouts
graylog_elasticsearch_cluster_discovery_timeout:       5000
graylog_elasticsearch_discovery_initial_state_timeout: '3s'
graylog_elasticsearch_request_timeout:                 '1m'
graylog_elasticsearch_connect_timeout:                 '10s'
graylog_index_ranges_cleanup_interval:                 '1h'
graylog_stream_processing_timeout:                     2000
graylog_output_module_timeout:                         10000
graylog_stale_master_timeout:                          2000
graylog_shutdown_timeout:                              30000
graylog_http_connect_timeout:                          '5s'
graylog_http_read_timeout:                             '10s'
graylog_http_write_timeout:                            '10s'
graylog_ldap_connection_timeout:                       2000
graylog_dashboard_widget_default_cache_time:           '10s'

# Content packs
graylog_content_packs_loader_enabled: 'True'
graylog_content_packs_dir:            '/usr/share/graylog-server/contentpacks'
graylog_content_packs_auto_load:      ''

# Buffer
graylog_udp_recvbuffer_sizes:                          1048576
graylog_ring_size:                                     65536
graylog_inputbuffer_ring_size:                         65536
graylog_inputbuffer_processors:                        2
graylog_inputbuffer_wait_strategy:                     'blocking'
graylog_outputbuffer_processor_keep_alive_time:        5000
graylog_outputbuffer_processor_threads_core_pool_size: 3
graylog_outputbuffer_processor_threads_max_pool_size:  30

# MongoDB
graylog_mongodb_uri:                                 'mongodb://127.0.0.1:27017/graylog'
graylog_mongodb_max_connections:                     100
graylog_mongodb_threads_allowed_to_block_multiplier: 5

# Drools
graylog_rules_file: ''

# Mail
graylog_transport_email_enabled:           'False'
graylog_transport_email_hostname:          ''
graylog_transport_email_port:              587
graylog_transport_email_use_auth:          'True'
graylog_transport_email_use_tls:           'True'
graylog_transport_email_use_ssl:           'True'
graylog_transport_email_auth_username:     ''
graylog_transport_email_auth_password:     ''
graylog_transport_email_subject_prefix:    '[graylog]'
graylog_transport_email_from_email:        ''
graylog_transport_email_web_interface_url: ''

# Proxy
graylog_http_proxy_uri:                    ''
graylog_proxied_requests_thread_pool_size: 32

# Web UI
graylog_web_enable:                  'True'
graylog_web_listen_uri:              'http://0.0.0.0:9000/'
graylog_web_endpoint_uri:            ''
graylog_enable_cors:                 'True'
graylog_enable_gzip:                 'True'
graylog_web_enable_tls:              'False'
graylog_web_tls_cert_file:           ''
graylog_web_tls_key_file:            ''
graylog_web_tls_key_password:        ''
graylog_web_max_header_size:         8192
graylog_web_max_initial_line_length: 4096
graylog_web_thread_pool_size:        16

# JVM
graylog_gc_warning_threshold: '1s'
graylog_server_java_opts:     '-Djava.net.preferIPv4Stack=true -Xms1500m -Xmx1500m -XX:NewRatio=1 -server -XX:+ResizeTLAB -XX:+UseConcMarkSweepGC -XX:+CMSConcurrentMTEnabled -XX:+CMSClassUnloadingEnabled -XX:+UseParNewGC -XX:-OmitStackTraceInFastThrow'
graylog_server_args:          ''
graylog_server_wrapper:       ''

# Install Switches
graylog_install_elasticsearch: true
graylog_install_mongodb:       True
graylog_install_nginx:         True

graylog_plugins: []

```

# Development

Please check [development guide](DEVELOPMENT.md) for details about developing and testing this role.

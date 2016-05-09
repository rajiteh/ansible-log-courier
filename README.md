ansible-log-courier
=========

Installs and configures [log-courier](https://github.com/driskell/log-courier)

Requirements
------------

None

Role Variables
--------------

## Required

* `cl_log_courier_ssl_certificate` : SSL Certificate for tls communication with the shipper (Required)
* `cl_log_courier_collectors` : Array of logstash servers

## Optional
    
    cl_log_courier_user: "root" # user the collector should run as
    cl_log_courier_config: "/etc/log-courier/log-courier.conf" # path to the configuration file (and folder) 
    cl_log_courier_monit_config_path: /etc/monit/conf.d/log-courier.conf # enables monit if defined
    cl_log_courier_log: "/var/log/log-courier.log" # log-courier log file path
    cl_log_courier_log_files: # log files to harvest from
      - paths: # Array of log files
          - "{{ cl_log_courier_log }}"
        fields: # Custom fields 
          type: "log-courier"
    #  - paths:
    #      - "/data/log/nginx/error.log"
    #    fields:
    #      type: "nginx_error"
    #      project: "main_app"

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - ansible-log-courier

License
-------

BSD


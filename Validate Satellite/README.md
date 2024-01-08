## Diagnose Satellite Services 

```
# satellite-maintain service list
Running Service List
================================================================================
List applicable services:
dynflow-sidekiq@.service                   indirect
foreman-proxy.service                      enabled
foreman.service                            enabled
httpd.service                              enabled
postgresql.service                         enabled
pulpcore-api.service                       enabled
pulpcore-content.service                   enabled
pulpcore-worker@.service                   indirect
redis.service                              enabled
tomcat.service                             enabled

All services listed                                                   [OK]
--------------------------------------------------------------------------------
```

## The satellite-maintain health check command runs various health checks in the Satellite Server installation.

```
# satellite-maintain health check
Running ForemanMaintain::Scenario::FilteredScenario
================================================================================
Check number of fact names in database:                               [OK]
--------------------------------------------------------------------------------
Check whether all services are running:                               [OK]
--------------------------------------------------------------------------------
Check whether all services are running using the ping call:           [OK]
--------------------------------------------------------------------------------
Check for paused tasks:                                               [OK]
--------------------------------------------------------------------------------
Check whether system is self-registered or not:                       [OK]
--------------------------------------------------------------------------------
```

## Use the hammer ping command in addition to the satellite-maintain service status command to diagnose and troubleshoot issues with Satellite services.

```
# hammer ping
database:
    Status:          ok
    Server Response: Duration: 0ms
candlepin:
    Status:          ok
    Server Response: Duration: 20ms
candlepin_auth:
    Status:          ok
    Server Response: Duration: 13ms
candlepin_events:
    Status:          ok
    message:         0 Processed, 0 Failed
    Server Response: Duration: 0ms
katello_events:
    Status:          ok
    message:         0 Processed, 0 Failed
    Server Response: Duration: 0ms
pulp3:
    Status:          ok
    Server Response: Duration: 29ms
pulp3_content:
    Status:          ok
    Server Response: Duration: 132ms
foreman_tasks:
    Status:          ok
    Server Response: Duration: 3ms
```


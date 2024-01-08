# Prerequisites

## Check timezone configuration.

```
# timedatectl status
               Local time: Mon 2024-01-08 01:53:23 UTC
           Universal time: Mon 2024-01-08 01:53:23 UTC
                 RTC time: Mon 2024-01-08 01:53:24
                Time zone: UTC (UTC, +0000)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: yes


# timedatectl set-timezone America/Mexico_City

# timedatectl status
               Local time: Sun 2024-01-07 19:56:12 CST
           Universal time: Mon 2024-01-08 01:56:12 UTC
                 RTC time: Sun 2024-01-07 19:56:12
                Time zone: America/Mexico_City (CST, -0600)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: yes

```

Note: You can check timezones with "# timedatectl list-timezones"

## On the host, update the subscription-manager and dnf packages to the latest versions.

```
# dnf update -y subscription-manager dnf
```

## Download the RPM from the Satellite Server.

```
# dnf localinstall -y http://satellite.mylab.com/pub/katello-ca-consumer-latest.noarch.rpm
```

## Register a Host to Satellite Server by Using the Consumer RPM.

```
# subscription-manager clean
# subscription-manager register --org organization_label
```

Example:

```
# subscription-manager clean
All local data removed

# subscription-manager register --org RedHat
Registering to: satellite.mylab.com:443/rhsm
Username: admin
Password:

The system has been registered with ID: f443007a-96c7-43f5-a7b5-0b3b754ca6b0
The registered system name is: rhel8901.mylab.com
```

## Install and use the Katello agent to manage packages and errata on the managed host.

```
# dnf install katello-agent
```
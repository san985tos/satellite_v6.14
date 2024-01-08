## Display Organizations

```
# hammer -u admin -p r3dh4t1! organization list
---|-----------|-----------|-------------|-------------------------------------
ID | TITLE     | NAME      | DESCRIPTION | LABEL
---|-----------|-----------|-------------|-------------------------------------
1  | “Default” | “Default” |             | 17141902-c6e9-4d88-a7d7-f019d077aa9c
---|-----------|-----------|-------------|-------------------------------------
```

## Show configuration file

```
# cat ~/.hammer/cli.modules.d/foreman.yml
:foreman:
  # Credentials. You'll be asked for the interactively if you leave them blank here
  :username: 'admin'
  :password: 'r3dh4t1!'
```

## This method avoids storing the credentials in unprotected scripts. To use this method, enable session use in your configuration file:

```
# echo '  :use_sessions: true' >> ~/.hammer/cli.modules.d/foreman.yml
# cat ~/.hammer/cli.modules.d/foreman.yml
:foreman:
  # Credentials. You'll be asked for the interactively if you leave them blank here
  :username: 'admin'
  :password: 'r3dh4t1!'
  :use_sessions: true
```

## Use the --help option to view subcommand actions.

```
# hammer organization --help
Usage:
    hammer organization [OPTIONS] SUBCOMMAND [ARG] ...

Parameters:
 SUBCOMMAND                    Subcommand
 [ARG] ...                     Subcommand arguments

Subcommands:
 add-compute-resource          Associate a compute resource
 add-domain                    Associate a domain
 add-hostgroup                 Associate a hostgroup
 add-location                  Associate a location
 add-medium                    Associate a medium
 add-provisioning-template     Associate provisioning templates
 add-smart-proxy               Associate a smart proxy
 add-subnet                    Associate a subnet
 add-user                      Associate an user
 configure-cdn                 Update the CDN configuration
 create                        Create organization
 delete                        Delete an organization
 delete-parameter              Delete parameter for an organization
 info                          Show organization
 list                          List all organizations
 remove-compute-resource       Disassociate a compute resource
 remove-domain                 Disassociate a domain
 remove-hostgroup              Disassociate a hostgroup
 remove-location               Disassociate a location
 remove-medium                 Disassociate a medium
 remove-provisioning-template  Disassociate provisioning templates
 remove-smart-proxy            Disassociate a smart proxy
 remove-subnet                 Disassociate a subnet
 remove-user                   Disassociate an user
 set-parameter                 Create or update parameter for an organization
 update                        Update organization

Options:
 -h, --help                    Print help
```

```
# hammer activation-key create --help
Usage:
    hammer activation-key create [OPTIONS]

Options:
 --auto-attach BOOLEAN                          Auto attach subscriptions upon registration
 --content-view[-id] VALUE/NUMBER               Content view name/id
 --description VALUE                            Description
 --environment[-id] VALUE/NUMBER                (--environment-id is deprecated: Use --lifecycle-environment-id instead)
 --lifecycle-environment[-id] VALUE/NUMBER      Environment name/id
 --max-hosts NUMBER                             Maximum number of registered content hosts
 --name VALUE                                   Name
 --organization[-id|-title|-label] VALUE/NUMBER Organization name/title/label/id
 --purpose-addons LIST                          Sets the system add-ons
 --purpose-role VALUE                           Sets the system purpose usage
 --purpose-usage VALUE                          Sets the system purpose usage
 --release-version VALUE                        Content release version
 --service-level VALUE                          Service level
 --unlimited-hosts                              Set hosts max to unlimited
 -h, --help                                     Print help

Option details:
  Here you can find option types and the value an option can accept:

  BOOLEAN             One of true/false, yes/no, 1/0
  DATETIME            Date and time in YYYY-MM-DD HH:MM:SS or ISO 8601 format
  ENUM                Possible values are described in the option's description
  FILE                Path to a file
  KEY_VALUE_LIST      Comma-separated list of key=value.
                      JSON is acceptable and preferred way for such parameters
  LIST                Comma separated list of values. Values containing comma should be quoted or escaped with backslash.
                      JSON is acceptable and preferred way for such parameters
  MULTIENUM           Any combination of possible values described in the option's description
  NUMBER              Numeric value. Integer
  SCHEMA              Comma separated list of values defined by a schema.
                      JSON is acceptable and preferred way for such parameters
  VALUE               Value described in the option's description. Mostly simple string
```



### REFERENCES
For more information, see the Hammer CLI Guide at https://access.redhat.com/documentation/en-us/red_hat_satellite/6.11/html-single/hammer_cli_guide/index

For more information, see the Hammer Cheat Sheet at https://access.redhat.com/documentation/en-us/red_hat_satellite/6.11/html-single/hammer_cheat_sheet/index
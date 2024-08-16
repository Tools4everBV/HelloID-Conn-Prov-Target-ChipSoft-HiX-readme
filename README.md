# HelloID-Conn-Prov-Target-ChipSoft-HiX

> [!WARNING]
> This connector has been tested on a ChipSoft-HiX environment in combination with HelloID. Although it can be implemented, implementations differ per organisation. Also various fixes will be implemented by the supplier in the near future. Therefore, changes will have to be made accordingly.

> [!WARNING]
> At this point, the security configuration for ChipSoft-HiX is not clear. The API connection itself has no security settings apart from an EV certificate that appears to be a server certificate only. This will need to be addressed before implementing this connector

> [!WARNING]
> When creating accounts in HIX, automatic logon is disabled. For now this should be activated manually. In ChipSoft HiX release HF86 this should be resolved and new accounts will be enabled for automatic logon.

> [!WARNING]
> When an usertype is set in HiX and the usertype will be changed during the employment to a empty usertype (mostly used for default employees), this cannot be done through the HiX API. An empty value cannot be set on an usertype that already has a value.

> [!WARNING]
> Current SSO state of users can't be retrieved from the API. Therefore SSO can only be set for all users or none of the users. Furthermore when setting the SSO-loginname (AzureUPN) send from HelloID to HIX and this does not correspond with the current value, the HIX API will remove the current SSO user and creates a new one. The comparison between the values will be processed in the HIX API and includes case-sensitivity (user@domain.com isn't the same as User@Domain.com). Be aware that deletion of the SSO user and the creation of the SSO can result in an error due timing-issues and can result in losing all current permissions in HIX.

> [!IMPORTANT]
> This repository contains the connector and configuration code only. The implementer is responsible to acquire the connection details such as username, password, certificate, etc. You might even need to sign a contract or agreement with the supplier before implementing this connector. Please contact the client's application manager to coordinate the connector requirements.

> [!IMPORTANT]
> When not using a mapping for translation of HR departmentcodes or jobtitlecodes to the corresponding HiX codes, the connector will use the existing HR codes. These codes should than exist in HiX.

<p align="center">
  <img src="https://chipsoft.nl/SiteCollectionImages/Chipsoft/svg/Logo%20ChipSoft.svg" width="600">
</p>

## Table of contents

- [HelloID-Conn-Prov-Target-ChipSoft-HiX](#helloid-conn-prov-target-chipsoft-hix)
  - [Table of contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Getting started](#getting-started)
    - [Provisioning PowerShell V2 connector](#provisioning-powershell-v2-connector)
      - [Correlation configuration](#correlation-configuration)
      - [Field mapping](#field-mapping)
    - [Connection settings](#connection-settings)
    - [Prerequisites](#prerequisites)
    - [Remarks](#remarks)
      - [HelloID Agent](#helloid-agent)
      - [Security](#security)
      - [Update always includes the full object](#update-always-includes-the-full-object)
      - [Maximum of characters on fields `title` and `department`](#maximum-of-characters-on-fields-title-and-department)
      - [`gebruikersnaam` and `ldap` both mapped to same value](#gebruikersnaam-and-ldap-both-mapped-to-same-value)
      - [Session concurrency](#session-concurrency)
      - [`ControlId`](#controlid)
  - [Getting help](#getting-help)
  - [HelloID docs](#helloid-docs)

## Introduction

_HelloID-Conn-Prov-Target-ChipSoft-HiX_ is a _target_ connector. _ChipSoft-HiX_ provides a SOAP WSDL interface that allow you to programmatically interact with its data. The HelloID connector uses the methods endpoints listed in the table below.

| Message type                   | Description                |
| ------------------------------ | -------------------------- |
| /nieuwegebruiker.gegevens      | Create a new user account. |
| /wijzigengebruiker.gegevens    | Modify a user account.     |
| /blokkerengebruiker.gegevens   | Disable a user account.    |
| /deblokkerengebruiker.gegevens | Enable a user account.     |
| /aanvraag.zisgebruikers        | Retrieve a user account.   |

The following lifecycle actions are available:

| Action                                       | Description                                                       |
| -------------------------------------------- | ----------------------------------------------------------------- |
| create.ps1                                   | PowerShell _create_ lifecycle action                              |
| delete.ps1                                   | PowerShell _delete_ lifecycle action                              |
| disable.ps1                                  | PowerShell _disable_ lifecycle action                             |
| enable.ps1                                   | PowerShell _enable_ lifecycle action                              |
| update.ps1                                   | PowerShell _update_ lifecycle action                              |
| permissions/groups/grantPermission.ps1       | PowerShell groups _grant_ lifecycle action                        |
| permissions/groups/revokePermission.ps1      | PowerShell groups _revoke_ lifecycle action                       |
| permissions/groups/permissions.ps1           | PowerShell groups _permissions_ lifecycle action                  |
| permissions/groups/subpermissions.ps1        | PowerShell groups _subpermissions_ lifecycle action               |
| permissions/logingroups/grantPermission.ps1  | PowerShell loginGroups _grant_ lifecycle action                   |
| permissions/logingroups/revokePermission.ps1 | PowerShell loginGroups _revoke_ lifecycle action                  |
| permissions/logingroups/permissions.ps1      | PowerShell loginGroups _permissions_ lifecycle action             |
| permissions/logingroups/subpermissions.ps1   | PowerShell loginGroups _subpermissions_ lifecycle action          |
| configuration.json                           | Default _configuration.json_                                      |
| fieldMapping.json                            | Default _fieldMapping.json_                                       |
| assets/hix_department_codes.csv              | Example of HR department - HiX department translation mapping     |
| assets/hix_jobtitle_codes.csv                | Example of HR jobtitle - HiX title translation mapping            |
| assets/hix_logingroups.csv                   | Example of mapped logingroups based on HR jobtitle and department |
| assets/hix_groups_codes.csv                  | Example of mapped groups based on HR jobtitle and department      |

## Getting started

### Provisioning PowerShell V2 connector

#### Correlation configuration

The correlation configuration is used to specify which properties will be used to match an existing account within ChipSoft-HiX* to a person in \_HelloID*.

To properly setup the correlation:

1. Open the `Correlation` tab.

2. Specify the following configuration:

   | Setting                   | Value                           |
   | ------------------------- | ------------------------------- |
   | Enable correlation        | `True`                          |
   | Person correlation field  | `PersonContext.Person.UserName` |
   | Account correlation field | `ldap`                          |

> [!TIP] > _For more information on correlation, please refer to our correlation [documentation](https://docs.helloid.com/en/provisioning/target-systems/powershell-v2-target-systems/correlation.html) pages_.

#### Field mapping

The field mapping can be imported by using the _fieldMapping.json_ file.

### Connection settings

The following settings are required to connect to the API.

| Setting | Description                                                                                       | Mandatory | Example                  |
| ------- | ------------------------------------------------------------------------------------------------- | --------- | ------------------------ |
| BaseUrl | The URL of the ChipSoft Gomez application server. (This address must also include a port number.) | Yes       | `http://127.0.0.1:12345` |

### Prerequisites

### Remarks

#### HelloID Agent

Because _ChipSoft HiX_ is an application that runs on-premises, the _HelloID_ agent is required in order to use this connector.

#### Security

At this point, the security configuration for ChipSoft-HiX is not clear. The API connection itself has no security settings apart from an EV certificate that appears to be a server certificate only. This will need to be addressed before implementing this connector.

#### Update always includes the full object

If a user is updated, the complete object must be send the API. The same applies to groups and loginGroups.

#### Maximum of characters on fields `title` and `department`

- The `title` field can only contain a maximum of _5_ characters.

- `department` field can only contain a maximum of _6_ characters.

> [!TIP]
> For both fields, this is being handled within the fieldMapping by using a complex mapping.

#### `gebruikersnaam` and `ldap` both mapped to same value

Currently we made the assumption that the `gebruikersnaam` and `ldap` properties will both be mapped to the same value. E.g. `$personContext.Person.UserName`.

> [!TIP]
> The `ldap` field is being used by _ChipSoft HiX_ to actually retrieve a user account. This is also the value that's being used for correlation.

#### Session concurrency

To ensure that the grant for groups and the grant for login groups do not interfere with each other, it's necessary to set concurrent actions to 1 for the connector. Otherwise, permissions may be overwritten or not properly assigned. This will also prevent actions in HIX will be executed while previous actions are not finished yet.

#### `ControlId`

All requests sent to the ChipSoft-HiX Gomez application server must include a unique identifier. Currently, this identifier is a combination of a GUID and the current timestamp. This will guarantee the `id` is always unique. This unique identifier will be verified within _ChipSoft-HiX_. If the numbers match, a response will be send back containing the same number. This number will be verified within the connector.

## Getting help

> [!TIP] > _For more information on how to configure a HelloID PowerShell connector, please refer to our [documentation](https://docs.helloid.com/en/provisioning/target-systems/powershell-v2-target-systems.html) pages_.

> [!TIP] > _If you need help, feel free to ask questions on our [forum](https://forum.helloid.com)_.

## HelloID docs

The official HelloID documentation can be found at: https://docs.helloid.com/

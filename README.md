# HelloID-Conn-Prov-Target-ChipSoft-HiX-readme

| :information_source: Contact |
|:---------------------------|
| Please contact your local Tools4ever sales representative for further information and details about the implementation of this connector  |

| :information_source: Information |
|:---------------------------|
| This repository contains the connector and configuration code only. The implementer is responsible to acquire the connection details such as username, password, certificate, etc. You might even need to sign a contract or agreement with the supplier before implementing this connector. Please contact the client's application manager to coordinate the connector requirements. |

<p align="center">
  <img src="https://www.tools4ever.nl/connector-logos/hix-logo.png" width="500">
</p>

## Table of contents

- [HelloID-Conn-Prov-Target-ChipSoft-HiX-readme](#helloid-conn-prov-target-chipsoft-hix-readme)
  - [Table of contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Getting started](#getting-started)
    - [LifeCycle events](#lifecycle-events)
    - [Connection settings](#connection-settings)
    - [Remarks](#remarks)
      - [HelloID Agent](#helloid-agent)
      - [Update user / groups](#update-user--groups)
      - [Creation / correlation process](#creation--correlation-process)
  - [Setup the connector](#setup-the-connector)
  - [Getting help](#getting-help)
  - [HelloID docs](#helloid-docs)

## Introduction

_HelloID-Conn-Prov-Target-ChipSoft-HiX_ is a _target_ connector. ChipSoft-HiX offers web services APIs that allow developers to access and integrate the functionality with other applications and systems.

The ChipSoft-HiX API uses a WSDL / SOAP architecture. A WSDL (Web Services Description Language) is an XML-based language that is used for describing the functionality of a web service. A WSDL file defines the methods that are exposed by the web service, along with the data types that are used by those methods and the messages that are exchanged between the web service and its clients.

## Getting started

### LifeCycle events

The following lifecycle events are available:

| Event| Description |
|---|---
| create.ps1 | Create (or update) and correlate an Account |
| update.ps1 | Update the Account |
| enable.ps1 | Enable the Account |
| disable.ps1 | Disable the Account |
| permissions.ps1 | Collects the possible permissions (Groups and LoginGroups) |
| grant.ps1 | Adds a member to a group or loginGroup |
| revoke.ps1 | Removes a member from a group or loginGroup |

> :exclamation: accounts cannot be deleted from ChipSoft-HiX.

### Connection settings

The following settings are required to connect to the API.

| Setting      | Description| Mandatory   |
| ------------ | -----------| ----------- |
| ServerAddress | The ServerAddress and port number to the COMEZ application server | Yes |


### Remarks

#### HelloID Agent

At this point the security configuration for ChipSoft-Hix is based on an EV certificate (Hix serverside only). If a client certificate is required, the connector can only be used in conjunction with the local HelloID provisioning agent.

#### Update user / groups

If a user is updated, the complete object must be send the API. The same applies to groups and loginGroups.

#### Creation / correlation process

A new functionality is the possibility to update the account in the target system during the correlation process. By default, this behavior is disabled. Meaning, the account will only be created or correlated.

You can change this behavior in the `create.ps1` by setting the boolean `$updatePerson` to the value of `$true`.

## Setup the connector

Because the update call to ChipSoft-HiX is in fact a 'PUT' and the user account first needs to be retrieved from ChipSoft-HiX, the concurrent sessions in HelloID must be set to the value of `1`.

## Getting help

> _For more information on how to configure a HelloID PowerShell connector, please refer to our [documentation](https://docs.helloid.com/hc/en-us/articles/360012558020-Configure-a-custom-PowerShell-target-system) pages_

> _If you need help, feel free to ask questions on our [forum](https://forum.helloid.com/forum/helloid-connectors/provisioning/1281-helloid-conn-prov-target-chipsoft-hix-readme)_


## HelloID docs

The official HelloID documentation can be found at: https://docs.helloid.com/

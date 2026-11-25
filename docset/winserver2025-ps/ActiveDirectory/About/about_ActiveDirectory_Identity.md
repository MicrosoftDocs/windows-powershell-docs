---
title: about_ActiveDirectory_Identity
ms.date: 04/22/2013
description: This article lists the identifying attributes that are used for search and retrieval supported by the Active Directory module for Windows PowerShell.
Locale: en-US
schema: 2.0.0
---

# about_ActiveDirectory_Identity

## SHORT DESCRIPTION

The Active Directory module for Windows PowerShell objects have a range of
identifying attributes that are used for search and retrieval.

## LONG DESCRIPTION

In order to identify the objects in Active Directory, each object has
attributes that can be used as identifiers. In the Active Directory module, the
value of the identity of an object can be passed using the Identity parameter.
Each object type has its own set of possible types and values for use by the
Identity parameter. See the detailed description of the Identity parameter of
the given cmdlet for more information about its usage.

When searching with the Active Directory module cmdlets, the value of the
Identity parameter, along with the values of the Server and Partition
parameters, is used to uniquely identify a single object. The Server parameter
is used to locate which server to connect with. The Partition parameter further
narrows the search to a specific partition. The Identity parameter then
resolves to a single unique object in the partition.

Note that using the Security Accounts Manager (SAM) Account Name
(**sAMAccountName**) when targeting a global catalog port, you will not find a
user in a different domain if you are using the Identity parameter

If more than one object is found using identity resolution, the Active
Directory module throws an error.

For more information about the Server and Partition parameters, see the help
topics for the individual cmdlets where they are used, such as `Get-ADUser`, by
typing:

```powershell
Get-Help Get-ADUser
```

### Objects and Identities

Each object has a list of attributes that can be used as an identity for that
object. Additionally, if the object inherits from another object, then the
parent object's identities can also be used as the child object's identities.
For more information on the Active Directory object hierarchy, see
[about_ActiveDirectory_ObjectModel](about_ActiveDirectory_ObjectModel.md).

> [!NOTE]
> For Active Directory Provider cmdlets, only an object's 'Distinguished Name'
> or 'Relative Distinguished Name' can be used as the identity. For a list of
> Active Directory Provider cmdlets, see ActiveDirectory.

### Identity Attributes

The following is a list of identity attributes by object type.

- ADAccount
  - Distinguished Name
  - GUID (objectGUID)
  - Security Identifier (objectSid)
  - SAM Account Name (sAMAccountName)

- ADComputer
  - Distinguished Name
  - GUID  (objectGUID)
  - Security Identifier (objectSid)
  - Security Accounts Manager Account Name (sAMAccountName)

- ADDirectoryServer
  - Name of the server object (name)
    - For AD LDS instances the syntax of a name is `<computer-name>$<instance-name>`
    - For other Active Directory instances, use the value of the name property.
  - Distinguished Name of the NTDS Settings object
  - Distinguished Name of the server object that represents the directory
    server.
  - GUID (objectGUID) of server object under the configuration partition.
  - GUID (objectGUID) of NTDS settings object under the configuration partition

- ADDomain
  - Distinguished Name
  - GUID
  - Security Identifier
  - DNS domain name
  - NetBIOS domain name

- ADDomainController
  - GUID (objectGUID)
  - IPV4Address
  - Global IPV6Address
  - DNS Host Name (dNSHostName)
  - Name of the server object
  - Distinguished Name of the NTDS Settings object
  - Distinguished Name of the server object that represents the domain controller
  - GUID of NTDS settings object under the configuration partition
  - GUID of server object under the configuration partition
  - Distinguished Name of the computer object that represents the domain controller.

- ADFineGrainedPasswordPolicy
  - Distinguished Name
  - GUID (objectGUID)
  - Name (name)

- ADForest
  - Fully qualified domain name
  - DNS host name
  - NetBIOS name

- ADGroup
  - Distinguished Name
  - GUID (objectGUID)
  - Security Identifier (objectSid)
  - Security Accounts Manager (SAM) Account Name (sAMAccountName)

- ADObject
  - Distinguished Name
  - GUID (objectGUID)

- ADOptionalFeature
  - Distinguished Name
  - Name (name)
  - Feature GUID (featureGUID)
  - GUID (objectGUID)

- ADOrganizationalUnit
  - Distinguished Name
  - GUID (objectGUID)

- ADPrincipal
  - Distinguished Name
  - GUID (objectGUID)
  - Security Identifier (objectSid)
  - SAM Account Name (sAMAccountName)

- ADServiceAccount
  - Distinguished Name
  - GUID (objectGUID)
  - Security Identifier (objectSid)
  - SAM Account Name (sAMAccountName)

- ADUser
  - Distinguished Name
  - GUID (objectGUID)
  - Security Identifier (objectSid)
  - SAM User Name (sAMUserName)


### Identities Formats

Active Directory module objects have a range of identity attributes. Below is a
list of these, their types and formats.

- Distinguished Name
  - Example: CN=SaraDavis,CN=Europe,CN=Users, DC=corp,DC=contoso,DC=com

- DNS domain name
  - Example: redmond.corp.contoso.com

- DNS Host Name (dNSHostName)
  - Example: corp-DC01.corp.contoso.com

- Feature GUID (featureGUID)
  - Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

- Fully qualified domain name
  - Example: corp.contoso.com

- Global IPV6Address
  - Example: 2001:4898:0:fff:200:5efe:157.59.132.61

- GUID (objectGUID)
  - Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

- IPV4Address
  - Example:157.59.132.61

- NetBIOS domain name
  - Example: redmond

- Name of the server object
  - Example: corp-DC01$

- SAM Account Name (sAMAccountName)
  - Example: saradavisreports

- Security Identifier (objectSid)
  - Example: S-1-5-21-3165297888-301567370-576410423-1103

- Name
  - Example: Recycle Bin Feature

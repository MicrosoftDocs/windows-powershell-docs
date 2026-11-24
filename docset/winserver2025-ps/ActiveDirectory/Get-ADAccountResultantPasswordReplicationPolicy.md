---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adaccountresultantpasswordreplicationpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADAccountResultantPasswordReplicationPolicy
---

# Get-ADAccountResultantPasswordReplicationPolicy

## SYNOPSIS
Gets the resultant password replication policy for an Active Directory account.

## SYNTAX

```
Get-ADAccountResultantPasswordReplicationPolicy [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-DomainController] <ADDomainController>
 [-Identity] <ADAccount> [-Partition <String>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ADAccountResultantPasswordReplicationPolicy` cmdlet gets the resultant password replication
policy for a user, computer, or service account on the specified read-only domain controller.

The policy is one of the following values:

- `Allow` or `1`
- `DenyExplicit` or `0`
- `DenyImplicit` or `2`
- `Unknown` or `-1`

The **Identity** parameter specifies the account. You can identify a user, computer, or service
account object by its distinguished name, GUID, security identifier (SID), or Security Account
Manager (SAM) account name. You can also set the **Identity** parameter to an account object
variable, such as `$<localAccountObject>`, or pass an account object through the pipeline to the
**Identity** parameter. For example, you can use the `Get-ADUser`, `Get-ADComputer`,
`Get-ADServiceAccount`, or `Search-ADAccount` cmdlets to retrieve an account object and then pass
the object through the pipeline to the `Get-ADAccountResultantPasswordReplicationPolicy` cmdlet.

The **DomainController** parameter specifies the read-only domain controller. You can identify a
domain controller by its IPV4Address, global IPV6Address, or DNS host name. You can also identify a
domain controller by the distinguished name of the NT Directory Services (NTDS) settings object or
the server object, the GUID of the NTDS settings object or the server object under the configuration
partition, or the distinguished name, **SamAccountName**, GUID, SID of the computer object that
represents the domain controller. You can also set the **DomainController** parameter to a domain
controller object variable, such as `$<localDomainControllerObject>`.

## EXAMPLES

### Example 1: Get the password replication policy for a specified user

```powershell
 Get-ADAccountResultantPasswordReplicationPolicy -Identity DavidChe -DomainController DC1
```

This command gets the password replication policy on the domain specified by the
**DomainController** parameter for the user account specified by the **Identity** parameter.

### Example 2: Get the password replication policy for a specified user using a distinguished name

```powershell
params = @{
    Identity = 'CN=Elisa Daugherty,OU=Europe,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM'
    DomainController = 'DC1'
}
 Get-ADAccountResultantPasswordReplicationPolicy @params
```

This command gets the password replication policy on the domain controller specified by the
**DomainController** parameter for the user account distinguished name specified by the **Identity**
parameter.

## PARAMETERS

### -AuthType

Specifies the authentication method to use.
The acceptable values for this parameter are:

- `Negotiate` or `0`
- `Basic` or `1`

The default authentication method is `Negotiate`.

A Secure Sockets Layer (SSL) connection is required for the `Basic` authentication method.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the user account credentials to use to perform this task. The default credentials are the
credentials of the currently logged on user unless the cmdlet is run from an Active Directory module
for Windows PowerShell provider drive. If the cmdlet is run from such a provider drive, the account
associated with the drive is the default.

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you can
specify a **PSCredential** object. If you specify a user name for this parameter, the cmdlet prompts
for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the **Credential** parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active
Directory module for Windows PowerShell returns a terminating error.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController

Specifies a read-only domain controller (RODC). The cmdlet returns the password replication policy
of the account for this RODC. You can identify the domain controller by providing one of the
following values:

- GUID (**objectGUID**)
- IPV4Address
- Global IPV6Address
- DNS Host Name (**dNSHostName**)
- Name of the server object
- A distinguished name of the NTDS Settings object
- A distinguished name of the server object that represents the domain controller
- GUID of NTDS settings object under the configuration partition
- GUID of server object under the configuration partition
- A distinguished Name of the computer object that represents the domain controller

> [!NOTE]
> The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for
> the attribute.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADDomainController
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies an Active Directory account object by providing one of the following property values. The
identifier in parentheses is the LDAP display name for the attribute. The acceptable values for this
parameter are:

- A distinguished name
- A GUID (**objectGUID**)
- A security identifier (**objectSid**)
- A SAM account name (**sAMAccountName**)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an
account object instance.

Derived types such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**

```yaml
Type: Microsoft.ActiveDirectory.Management.ADAccount
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Partition

Specifies the distinguished name of an Active Directory partition. The distinguished name must be
one of the naming contexts on the current directory server. The cmdlet searches this partition to
find the object defined by the **Identity** parameter.

In many cases, a default value is used for the **Partition** parameter if no value is specified. The
rules for determining the default value are given below. Note that rules listed first are evaluated
first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services environments, a default value for **Partition** is set in the
following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition**
  is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is
  automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of **Partition** is set to the default
  partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for
**Partition** is set in the following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition**
  is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is
  automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of **Partition** is
  set to the default naming context. To specify a default naming context for an AD LDS environment,
  set the `msDS-defaultNamingContext` property of the Active Directory directory service agent
  (DSA) object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the **Partition** parameter will not take any default value.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the Active Directory Domain Services instance to connect to, by providing one of the
following values for a corresponding domain name or directory server. The service may be any of the
following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active
Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that
they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows
  PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADAccount

An account object is received by the **Identity** parameter.

Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADResultantPasswordReplicationPolicy

This cmdlet returns an **ADResultantPasswordReplicationPolicy** enum value that represents the
resultant password replication policy for an account on the specified domain controller.

## NOTES

- This cmdlet doesn't work with AD LDS.
- This cmdlet doesn't work with an Active Directory snapshot.

## RELATED LINKS

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Get-ADUser](./Get-ADUser.md)

[Search-ADAccount](./Search-ADAccount.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

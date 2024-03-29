---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-addomaincontrollerpasswordreplicationpolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADDomainControllerPasswordReplicationPolicy
---

# Get-ADDomainControllerPasswordReplicationPolicy

## SYNOPSIS
Gets the members of the allowed list or denied list of a read-only domain controller's password replication policy.

## SYNTAX

### AllowedPRP (Default)
```
Get-ADDomainControllerPasswordReplicationPolicy [-Allowed] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADDomainController> [-Server <String>] [<CommonParameters>]
```

### DeniedPRP
```
Get-ADDomainControllerPasswordReplicationPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Denied]
 [-Identity] <ADDomainController> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADDomainControllerPasswordReplicationPolicy** cmdlet gets the users, computers, service accounts and groups that are members of the applied list or denied list for a read-only domain controller's (RODC) password replication policy.
To get the members of the applied list, specify the *AppliedList* parameter.
To get the members of the denied list, specify the *DeniedList* parameter.

The *Identity* parameter specifies the RODC that uses the allowed and denied lists to apply the password replication policy.
You can identify a domain controller by its GUID, IPV4Address, IPV6Address, or DNS host name.
You can also identify a domain controller by the name of the server object that represents the domain controller, the distinguished name of the NTDS settings object or the server object, the GUID of the NTDS settings object or the server object under the configuration partition, or the distinguished name of the computer object that represents the domain controller.

You can also set the *Identity* parameter to a domain controller object variable, such as `$<localDomainControllerObject>`, or pass a domain controller object through the pipeline operator to the *Identity* parameter.
For example, you can use the **Get-ADDomainController** cmdlet to retrieve a domain controller object and then pass the object through the pipeline operator to the **Get-ADDomainControllerPasswordReplicationPolicy** cmdlet.

If you specify a writeable domain controller for this cmdlet, the cmdlet returns a non-terminating error.

## EXAMPLES

### Example 1: gets from an RODC domain controller password replication policy the allowed accounts showing the name and object class of each
```
PS C:\> Get-ADDomainControllerPasswordReplicationPolicy -Identity "USER01-RODC1" -Allowed | ft Name,ObjectClass
```

This command gets from an RODC domain controller password replication policy the allowed accounts showing the name and object class of each.

### Example 2: Get the password replication policy allowed list from all RODCs in the domain
```
C:\PS>Get-ADDomainController -Filter "IsReadOnly -eq `$true" | Get-ADDomainControllerPasswordReplicationPolicy -Allowed

DistinguishedName : CN=Allowed RODC Password Replication Group,CN=Users,DC=Fabrikam,DC=com
Name              : Allowed RODC Password Replication Group
ObjectClass       : group
ObjectGUID        : 239b0470-7f49-472d-8fcb-4911e90b2c5e
SamAccountName    : Allowed RODC Password Replication Group
SID               : S-1-5-21-41432690-3719764436-1984117282-571
```

This command gets the password replication policy allowed lists from all RODCs in the domain.

## PARAMETERS

### -Allowed
Specifies a search for accounts that have been authenticated by a read-only domain controller.

```yaml
Type: SwitchParameter
Parameter Sets: AllowedPRP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
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
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

Specifies the credentials for the security context under which the task is performed.
If this security context doesn't have directory level permissions to perform the task, then an error is returned by the directory.
If running under the context of an Active Directory module for Windows PowerShell provider drive, the credentials information associated with the drive is used as the default value; otherwise, the currently logged on user security context is used.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Denied
Specifies the users, computers, groups or other accounts to add to the list of accounts that are denied the right to replicate their passwords to this read-only domain controller (RODC).
You can specify more than one value by using a comma-separated list.
The acceptable values for this parameter are:

- A distinguished name
- A GUID  (objectGUID) 
- A security identifier (objectSid) 
- A SAM account name (sAMAccountName)

```yaml
Type: SwitchParameter
Parameter Sets: DeniedPRP
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory domain controller object by providing one of the following values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute. 
The acceptable values for this parameter are:

- A GUID (objectGUID) 
- An IPV4Address
- A Global IPV6Address 
- A DNS Host Name (dNSHostName) 
- A name of the server object
- A Distinguished Name of the NTDS Settings object
- A distinguished name of the server object that represents the domain controller
- A GUID of NTDS settings object under the configuration partition
- A GUID of server object under the configuration partition
- A distinguished name of the computer object that represents the domain controller.

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADDomainController
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways: 

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values: 

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [About CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADDomainController
A domain controller object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADPrincipal
Returns one or more objects that represent the users, computers, service accounts, and groups that are members of the applied list or denied list of the domain controller password replication policy.
The list returned depends on the parameters specified.

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services.
* This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Add-ADDomainControllerPasswordReplicationPolicy](./Add-ADDomainControllerPasswordReplicationPolicy.md)

[Remove-ADDomainControllerPasswordReplicationPolicy](./Remove-ADDomainControllerPasswordReplicationPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./ActiveDirectory.md)


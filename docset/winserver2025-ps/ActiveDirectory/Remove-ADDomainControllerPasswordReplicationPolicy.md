---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/remove-addomaincontrollerpasswordreplicationpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ADDomainControllerPasswordReplicationPolicy
---

# Remove-ADDomainControllerPasswordReplicationPolicy

## SYNOPSIS
Removes users, computers, and groups from the allowed or denied list of a read-only domain controller password replication policy.

## SYNTAX

### AllowedPRP
```
Remove-ADDomainControllerPasswordReplicationPolicy [-WhatIf] [-Confirm] -AllowedList <ADPrincipal[]>
 [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADDomainController> [-PassThru]
 [-Server <String>] [<CommonParameters>]
```

### DeniedPRP
```
Remove-ADDomainControllerPasswordReplicationPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] -DeniedList <ADPrincipal[]> [-Identity] <ADDomainController> [-PassThru]
 [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ADDomainControllerPasswordReplicationPolicy** cmdlet removes one or more users, computers, and groups from the allowed or denied list of a read-only domain controller (RODC) password replication policy.

The *Identity* parameter specifies the RODC that uses the allowed and denied lists to apply the password replication policy.
You can identify a domain controller by its GUID, IPV4Address, global IPV6Address, or DNS host name.
You can also identify a domain controller by the name of the server object that represents the domain controller, the distinguished name of the NTDS settings object or the server object, the GUID of the NTDS settings object or the server object under the configuration partition, or the distinguished name of the computer object that represents the domain controller.
You can also set the *Identity* parameter to a domain controller object variable, such as `$<localDomainControllerObject>`, or pass a domain controller object through the pipeline operator to the *Identity* parameter.
For example, you can use the **Get-ADDomainController** cmdlet to retrieve a domain controller object and then pass the object through the pipeline operator to the **Remove-ADDomainControllerPasswordReplicationPolicy** cmdlet.
You must provide a read-only domain controller.

The *AllowedList* parameters specify the users, computers and groups to remove from the allowed list.
Similarly, the *DeniedList* parameter specifies the users, computers and groups to remove from the denied list.
You must specify either one or both of the *AllowedList* and *DeniedList* parameters.
You can identify a user, computer or group by distinguished name (DN), GUID, security identifier (SID) or security accounts manager (SAM) account name.
You can also specify user, computer or group variables, such as `$<localUserObject>`.
If you are specifying more than one item, use a comma-separated list.

## EXAMPLES

### Example 1: Remove specific users from the Allowed list on a RODC
```
PS C:\> Remove-ADDomainControllerPasswordReplicationPolicy -Identity "USER01-RODC1" -AllowedList "PattiFuller", "DavidChew"
```

This command removes the users with samAccountNames PattiFuller and DavidChew from the Allowed list on the RODC USER01-RODC1.

### Example 2: Remove specific users from the Denied list on a RODC
```
PS C:\> Remove-ADDomainControllerPasswordReplicationPolicy -Identity "USER01-RODC1" -DeniedList "ElisaDaugherty", "EvanNarvaez"
```

This command removes the users with samAccountNames Elisa Daugherty and Evan Narvaez from the Denied list on the RODC FABRIKAM-RODC1.

## PARAMETERS

### -AllowedList
Specifies the users, computers, groups or other accounts to add to the list of accounts allowed to replicate their passwords to this RODC.
You can specify more than one value by using a comma-separated list.
The acceptable values for this parameter are:

- A distinguished name
- A GUID  (objectGUID)
- A security identifier (objectSid)
- A Security Accounts Manager (SAM) account name  (sAMAccountName)

```yaml
Type: ADPrincipal[]
Parameter Sets: AllowedPRP
Aliases:

Required: True
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -DeniedList
Specifies the users, computers, groups or other accounts to add to the list of accounts that are denied the right to replicate their passwords to this RODC.
You can specify more than one value by using a comma-separated list.
The acceptable values for this parameter are:

- A distinguished name
- A GUID  (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

```yaml
Type: ADPrincipal[]
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
- A  name of the server object
- A distinguished name of the NTDS Settings object
- A distinguished name of the server object that represents the domain controller
- A GUID of NTDS settings object under the configuration partition
- A GUID of server object under the configuration partition
- A distinguished name of the computer object that represents the domain controller

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomainController
A read-only domain controller object is received by the *Identity* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomainController
This cmdlet returns the modified read-only domain controller object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.
* By default, this cmdlet has the *Confirm* parameter set, which prompts you to confirm before a removal of the specified object type can occur. To bypass prompting for confirmation before removal, you can specify `-Confirm:$False` when using this cmdlet.

## RELATED LINKS

[Add-ADDomainControllerPasswordReplicationPolicy](./Add-ADDomainControllerPasswordReplicationPolicy.md)

[Get-ADDomainController](./Get-ADDomainController.md)

[Get-ADDomainControllerPasswordReplicationPolicy](./Get-ADDomainControllerPasswordReplicationPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)


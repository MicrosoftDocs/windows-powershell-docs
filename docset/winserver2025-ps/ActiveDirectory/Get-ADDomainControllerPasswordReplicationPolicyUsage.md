---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-addomaincontrollerpasswordreplicationpolicyusage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADDomainControllerPasswordReplicationPolicyUsage
---

# Get-ADDomainControllerPasswordReplicationPolicyUsage

## SYNOPSIS
Gets the Active Directory accounts that are authenticated by a read-only domain controller or that are in the revealed list of the domain controller.

## SYNTAX

### RevealedAccounts (Default)
```
Get-ADDomainControllerPasswordReplicationPolicyUsage [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADDomainController> [-RevealedAccounts] [-Server <String>] [<CommonParameters>]
```

### AuthenticatedAccounts
```
Get-ADDomainControllerPasswordReplicationPolicyUsage [-AuthenticatedAccounts] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADDomainController> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADDomainControllerPasswordReplicationPolicyUsage** cmdlet gets the user or computer accounts that are authenticated by a read-only domain controller (RODC) or that have passwords that are stored on that RODC.
The list of accounts that are stored on a RODC is known as the revealed list.

To get accounts that are authenticated by the RODC, use the **AuthenticatedAccounts** parameter.
To get the accounts that have passwords stored on the RODC, use the **RevealedAccounts** parameter.

The **Identity** parameter specifies the RODC.
You can identify a domain controller by its GUID, IPV4Address, global IPV6Address, or DNS host name.
You can also identify a domain controller by the name of the server object that represents the domain controller, the distinguished name distinguished name of the NTDS settings object of the server object, the GUID of the NTDS settings object of the server object under the configuration partition, or the distinguished name of the computer object that represents the domain controller.
You can also set the **Identity** parameter to a domain controller object variable, such as **$\<localDomainControllerObject\>**, or pass a domain controller object through the pipeline to the **Identity** parameter.
For example, you can use the Get-ADDomainController  cmdlet to retrieve a domain controller object and then pass the object through the pipeline to the **Get-ADDomainControllerPasswordReplicationPolicyUsage** cmdlet.
If you specify a writeable domain controller for this cmdlet, the cmdlet returns a non-terminating error.

## EXAMPLES

### Example 1: Get authenticated accounts for a specific RODC
```
PS C:\> Get-ADDomainControllerPasswordReplicationPolicyUsage -Identity "USER01-RODC1" -AuthenticatedAccounts | ft Name,ObjectClass -A
```

This command gets the authenticated accounts for the RODC specified by the **Identity** parameter.
The command displays the name and object class of each.

### Example 2: Get revealed accounts for a specified RODC
```
PS C:\> Get-ADDomainControllerPasswordReplicationPolicyUsage -Identity "USER01-RODC1" -RevealedAccounts | ft Name,ObjectClass -A
```

This command gets the revealed accounts for the RODC specified by the **Identity** parameter.
The command displays the name and object class of each account returned.

### Example 3: Get a list of accounts cached across all RODCs
```
PS C:\> Get-ADDomainController -Filter "IsReadOnly -eq `$true" | Get-ADDomainControllerPasswordReplicationPolicyUsage
DistinguishedName : CN=krbtgt_35512,CN=Users,DC=User01,DC=com
Enabled           : False
Name              : krbtgt_35512
ObjectClass       : user
ObjectGUID        : 8c7268f9-add3-409c-968b-de029e517211
SamAccountName    : krbtgt_35512
SID               : S-1-5-21-41432690-3719764436-1984117282-1106
UserPrincipalName :

DistinguishedName : CN=CSD2722780,OU=Domain Controllers,DC=User01,DC=com
Enabled           : True
Name              : CSD2722780
ObjectClass       : computer
ObjectGUID        : 63a5e005-e01f-4fc9-ae71-9d9367f808bc
SamAccountName    : CSD2722780$
SID               : S-1-5-21-41432690-3719764436-1984117282-1105
UserPrincipalName :
```

This command gets the list of accounts cached across all RODCs in the domain.

## PARAMETERS

### -AuthenticatedAccounts
Specifies a search for accounts that have been authenticated by a read-only domain controller.

```yaml
Type: SwitchParameter
Parameter Sets: AuthenticatedAccounts
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


### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

Specifies the credentials for the security context under which the task is performed.
If this security context doesn't have directory level permissions to perform the task, then an error is returned by the directory.
If running under the context of an Active Directory module for Windows PowerShell provider drive, the credentials information associated with the drive is used as the default value; otherwise, the currently logged on user security context is used.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the **Credential** parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

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

### -Identity
Specifies an Active Directory domain controller object by providing one of the following values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A GUID (objectGUID).
- An IPV4Address.
- A Global IPV6Address.
- A DNS Host Name (dNSHostName).
- A name of the server object.
- A distinguished name of the NTDS Settings object.
- A distinguished name of the server object that represents the domain controller.
- A GUID of NTDS settings object under the configuration partition.
- A GUID of server object under the configuration partition.
- A distinguished name of the computer object that represents the domain controller.

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get the object through the pipeline or you can set this parameter to an object instance.

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

### -RevealedAccounts
Specifies a search for accounts which have passwords that are stored on the read-only domain controller.

```yaml
Type: SwitchParameter
Parameter Sets: RevealedAccounts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services, or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name.
- NetBIOS name.

Directory server values:

- Fully qualified directory server name.
- NetBIOS name.
- Fully qualified directory server name and port.

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the **Server** value from objects passed through the pipeline.
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive when the cmdlet runs in that drive.
- By using the domain of the computer running Windows PowerShell.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADDomainController
A domain controller object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADAccount
This cmdlet returns one or more account objects that represent the users, computers, and service accounts that are authenticated by the specified RODC or that have passwords that are stored on the RODC.

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work when targeting a snapshot using the *Server* parameter.

## RELATED LINKS

[Get-ADDomainController](./Get-ADDomainController.md)

[Add-ADDomainControllerPasswordReplicationPolicy](./Add-ADDomainControllerPasswordReplicationPolicy.md)

[Get-ADDomainControllerPasswordReplicationPolicy](./Get-ADDomainControllerPasswordReplicationPolicy.md)

[Remove-ADDomainControllerPasswordReplicationPolicy](./Remove-ADDomainControllerPasswordReplicationPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)


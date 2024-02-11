---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 06/11/2021
online version: https://learn.microsoft.com/powershell/module/activedirectory/remove-adgroupmember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ADGroupMember
---

# Remove-ADGroupMember

## SYNOPSIS
Removes one or more members from an Active Directory group.

## SYNTAX

```
Remove-ADGroupMember [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADGroup> [-Members] <ADPrincipal[]> [-Partition <String>] [-PassThru] [-Server <String>]
 [-DisablePermissiveModify] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ADGroupMember** cmdlet removes one or more users, groups, service accounts, or computers from an Active Directory group.

The *Identity* parameter specifies the Active Directory group that contains the members to remove.
You can identify a group by its distinguished name, GUID, security identifier, or Security Account Manager (SAM) account name.
You can also specify a group object variable, such as `$<localGroupObject>`, or pass a group object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADGroup** cmdlet to retrieve a group object and then pass the object through the pipeline to the Remove-ADGroupMember cmdlet.

The *Members* parameter specifies the users, computers and groups to remove from the group specified by the *Identity* parameter.
You can identify a user, computer or group by its distinguished name, GUID, security identifier, or SAM account name.
You can also specify user, computer, and group object variables, such as `$<localUserObject>`.
If you are specifying more than one new member, use a comma-separated list.
You cannot pass user, computer, or group objects through the pipeline to this cmdlet.
To remove user, computer, or group objects from a group by using the pipeline, use the Remove-ADPrincipalGroupMembership cmdlet.

For Active Directory Lightweight Directory Services (AD LDS) environments, the *Partition* parameter must be specified except in the following two conditions:

- The cmdlet is run from an Active Directory provider drive.
- A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.

## EXAMPLES

### Example 1: Remove a member from a group
```
PS C:\> Remove-ADGroupMember -Identity DocumentReaders -Members DavidChew
Confirm
Are you sure you want to perform this action?
Performing operation "Set" on Target "CN=DocumentReaders,CN=Users,DC=Fabrikam,DC=com".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command removes the user with the SAM account name DavidChew from the group DocumentReaders.

### Example 2: Remove multiple members from a group
```
PS C:\> Remove-ADGroupMember -Identity "DocumentReaders" -Members administrator,DavidChew
```

This command removes the users with SAM account name administrator and DavidChew from the group DocumentReaders.

### Example 3: Remove a distinguished user from a group
```
PS C:\> Get-ADGroup -Server localhost:60000 -Identity CN=AccessControl,DC=AppNC | Remove-ADGroupMember -Members CN=GlenJohn,DC=AppNC
Confirm
Are you sure you want to perform this action?
Performing operation "Set" on Target "CN=AccessControl,DC=AppNC".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command removes the user with the distinguished name CN=GlenJohn,DC=AppNC from the group AccessControl on an AD LDS instance using the pipeline.

## PARAMETERS

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
Default value: True
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

### -DisablePermissiveModify
Group membership updates use permissive modify by default. This suppresses an error when removing a member that is not member of the group.
When this parameter is used, an error "The specified account name is not a member of the group" is returned.

This parameter is available in Windows Server 2019 with the September 2020 Updates.


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory group object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A Security Account Manager account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADGroup
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Members
Specifies an array of user, group, and computer objects in a comma-separated list to remove from a group.
To identify each object, use one of the following property values.
Note: The identifier in parentheses is the LDAP display name.
The acceptable values for this parameter are:

- Distinguished name
- GUID (objectGUID)
- Security identifier (objectSid)
- SAM account name (sAMAccountName)

You can also provide objects to this parameter directly.

The following examples show how to specify this parameter.

This example specifies a user and group to remove by specifying the distinguished name and the SAM account name properties.

`-Members "CN=SaraDavis,CN=employees,CN=Users,DC=contoso,DC=com", "saradavisreports"`

This example specifies a user and a group object that are defined in the current Windows PowerShell session as input for the parameter.

`-Members $userObject, $GroupObject`

The objects specified for this parameter are processed as **Microsoft.ActiveDirectory.Management.ADPrincipal** objects.
Derived types, such as the following, are also received by this parameter.

- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADGroup**

You cannot pass objects through the pipeline to this parameter.

```yaml
Type: ADPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Partition
Specifies the distinguished name of an Active Directory partition.
The distinguished name must be one of the naming contexts on the current directory server.
The cmdlet searches this partition to find the object defined by the *Identity* parameter.

In many cases, a default value is used for the *Partition* parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter does not take a default value.

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
Specifies the AD DS instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: AD LDS, AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the AD DS Windows PowerShell provider drive, when the cmdlet runs in that drive
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

### -DisablePermissiveModify
Group membership updates use permissive modify by default. This suppresses an error when removing a member that is not member of the group.
When this parameter is used, an error "The specified account name is not a member of the group" is returned.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Required: False
Position: Named
Default value: False
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

### None or Microsoft.ActiveDirectory.Management.ADGroup
A group object is received by the *Identity* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADGroup
Returns the modified group object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.
* By default, this cmdlet has the *Confirm* parameter set, which prompts you to confirm before a removal of the specified object type can occur. To bypass prompting for confirmation before removal, you can specify `-Confirm:$False` when using this cmdlet.

## RELATED LINKS

[Add-ADGroupMember](./Add-ADGroupMember.md)

[Add-ADPrincipalGroupMembership](./Add-ADPrincipalGroupMembership.md)

[Get-ADGroup](./Get-ADGroup.md)

[Get-ADGroupMember](./Get-ADGroupMember.md)

[Get-ADPrincipalGroupMembership](./Get-ADPrincipalGroupMembership.md)

[Remove-ADPrincipalGroupMembership](./Remove-ADPrincipalGroupMembership.md)


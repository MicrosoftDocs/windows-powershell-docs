---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/remove-adprincipalgroupmembership?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ADPrincipalGroupMembership
---

# Remove-ADPrincipalGroupMembership

## SYNOPSIS
Removes a member from one or more Active Directory groups.

## SYNTAX

```
Remove-ADPrincipalGroupMembership [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADPrincipal> [-MemberOf] <ADGroup[]> [-Partition <String>] [-PassThru] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ADPrincipalGroupMembership** cmdlet removes a user, group, computer, service account, or any other account object from one or more Active Directory groups.

The *Identity* parameter specifies the user, group, or computer to remove.
You can identify the user, group, or computer by its distinguished name, GUID, security identifier (SID), or Security Account Manager (SAM) account name.
You can also specify a user, group, or computer object variable, such as `$<localGroupObject>`, or pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADUser** cmdlet to get a user object and then pass the object through the pipeline to the **Remove-ADPrincipalGroupMembership** cmdlet.
Similarly, you can use Get-ADGroup or Get-ADComputer to get group, service account, and computer objects to pass through the pipeline.

This cmdlet collects all of the user, computer, service account, and group objects from the pipeline, and then removes these objects from the specified group by using one Active Directory operation.

The *MemberOf* parameter specifies the groups that you want to remove the member from.
You can identify a group by its distinguished name, GUID, security identifier, or SAM account name.
You can also specify group object variable, such as `$<localGroupObject>`.
To specify more than one group, use a comma-separated list.
You cannot pass group objects through the pipeline to the MemberOf parameter.
To remove a member from groups that are passed through the pipeline, use Remove-ADGroupMember cmdlet.

## EXAMPLES

### Example 1: Remove a user from a group
```
PS C:\> Remove-ADPrincipalGroupMembership -Identity "David Chew" -MemberOf "Administrators"
Remove members from group
Do you want to remove all the specified member(s) from the specified group(s)?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
```

This command removes the user David Chew from the Administrators group.

### Example 2: Remove a user from a distinguished name group
```
PS C:\> Get-ADUser -Server localhost:60000 -Identity "CN=GlenJohns,DC=AppNC" | Remove-ADPrincipalGroupMembership -MemberOf "CN=AccessControl,DC=AppNC"
```

This command retrieves the user with the distinguished name CN=DavidChew,DC=AppNC and removes it from the group with the distinguished name CN=AccessControl,DC=AppNC by using the pipeline operator.

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory PowerShell returns a terminating error.

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
Specifies an Active Directory principal object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**

```yaml
Type: ADPrincipal
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemberOf
Specifies the Active Directory groups to remove a user, computer, or group to as a member.
You can identify a group by providing one of the following values.
Note: The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

If you are specifying more than one group, use commas to separate the groups in the list.

```yaml
Type: ADGroup[]
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

In many cases, a default value will be used for the *Partition* parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter does not take any default value.

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

### None or Microsoft.ActiveDirectory.Management.ADPrincipal
A principal object that represents user, computer, or group is received by the *Identity* parameter.
Derived types, such as the following are also received by this parameter.

- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADGroup**

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADPrincipal
Returns a principal object that represents the modified user, computer or group object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.
* By default, this cmdlet has the *Confirm* parameter set, which prompts you to confirm before a removal of the specified object type can occur. To bypass prompting for confirmation before removal, you can specify `-Confirm:$False` when using this cmdlet.

## RELATED LINKS

[Add-ADGroupMember](./Add-ADGroupMember.md)

[Add-ADPrincipalGroupMembership](./Add-ADPrincipalGroupMembership.md)

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADGroup](./Get-ADGroup.md)

[Get-ADGroupMember](./Get-ADGroupMember.md)

[Get-ADPrincipalGroupMembership](./Get-ADPrincipalGroupMembership.md)

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Get-ADUser](./Get-ADUser.md)

[Remove-ADGroupMember](./Remove-ADGroupMember.md)


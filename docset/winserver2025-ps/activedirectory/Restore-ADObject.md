---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/restore-adobject?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-ADObject
---

# Restore-ADObject

## SYNOPSIS
Restores an Active Directory object.

## SYNTAX

```
Restore-ADObject [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADObject> [-NewName <String>] [-Partition <String>] [-PassThru] [-Server <String>]
 [-TargetPath <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-ADObject** cmdlet restores a deleted Active Directory object.

The *NewName* parameter specifies the new name for the restored object.
If the *NewName* parameter is not specified, the value of the Active Directory attribute with an Lightweight Directory Access Protocol (LDAP) display name of msDS-lastKnownRDN is used.
The *TargetPath* parameter specifies the new location for the restored object.
If the *TargetPath* is not specified, the value of the Active Directory attribute with an LDAP display name of lastKnownParent is used.

The *Identity* parameter specifies the Active Directory object to restore.
You can identify an object by its distinguished name or GUID.
You can also set the *Identity* parameter to an object variable such as `$<localObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADObject** cmdlet to get a deleted object by specifying the *IncludeDeletedObjects* parameter.
You can then pass the object through the pipeline to the Restore-ADObject cmdlet.

Note: You can get the distinguished names of deleted objects by using the **Get-ADObject** cmdlet with the *IncludeDeletedObjects* parameter specified.

## EXAMPLES

### Example 1: Restore an object and set attributes for the deleted object
```
PS C:\> Restore-ADObject -Identity "613dc90a-2afd-49fb-8bd8-eac48c6ab59f" -NewName "Kim Abercrombie" -TargetPath "OU=Finance,OU=UserAccounts,DC=FABRIKAM,DC=COM"
```

This command restores the **ADObject** while setting the **msDS-LastKnownRDN** attribute of the deleted object to the *NewName* parameter and setting the lastKnownRDN to the *TargetPath* parameter.

### Example 2: Restore an object by distinguished name
```
PS C:\> Restore-ADObject -Identity "CN=Kim Abercrombie\0ADEL:613dc90a-2afd-49fb-8bd8-eac48c6ab59f,CN=Deleted Objects,DC=FABRIKAM,DC=COM" -NewName "Kim Abercrombie" -TargetPath "OU=Finance,OU=UserAccounts,DC=FABRIKAM,DC=COM"
```

This command restores the **ADObject** while setting the **msDS-LastKnownRDN** attribute of the deleted object to *NewName* parameter and setting the lastKnownRDN to the *TargetPath* parameter.

### Example 3: Restore an object from a filtered list of users
```
PS C:\> Get-ADObject -Filter 'samaccountname -eq "pattifuller"' -IncludeDeletedObjects | Restore-ADObject
```

This command finds a deleted user whose SAM account name is pattifuller and restores it.

### Example 4: Restore an object by its GUID
```
PS C:\> Restore-ADObject -Identity '6bb3bfe9-4355-48ee-b3b6-4fda6917d31d' -Server server1:50000
```

This command restores an AD LDS object using ObjectGUID.

### Example 5: Restore an object by its msds-LastKnownRDN attribute
```
PS C:\> Get-ADObject -Filter 'msds-lastknownrdn -eq "user1"' -Server server1:50000 -IncludeDeletedObjects -SearchBase "o=app1,c=us" | Restore-ADObject
```

This command restores an AD LDS object using the **msds-LastKnownRDN** attribute.

### Example 6: Restore deleted Configuration objects in a certain date/time range
```
PS C:\> $ChangeDate = New-Object DateTime(2008, 11, 18, 1, 40, 02)
PS C:\> Get-ADObject -Filter 'whenChanged -gt $ChangeDate -and isDeleted -eq $True -and -not (isRecycled -eq $True) -and lastKnownParent -eq "OU=Accounting,DC=Fabrikam,DC=com"' -IncludeDeletedObjects -SearchBase "CN=Deleted Objects,CN=Configuration,DC=contoso,DC=com" | Restore-ADObject
```

This command restores deleted configuration objects in a certain date/time range. This will be Helpful if you know when these objects were deleted.

### Example 7: Restore all deleted Configuration objects

```
Get-ADObject -filter 'isdeleted -eq $true -and name -ne "Deleted Objects"' -includeDeletedObjects -property * -SearchBase "CN=Deleted Objects,CN=Configuration,DC=contoso,DC=com" | Restore-ADObject
```

This command restores all deleted configuration objects.

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
Type: ADObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewName
Specifies the new name of the object.
This parameter sets the **Name** property of the Active Directory object.
The LDAP display name (**ldapDisplayName**) of this property is name.

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

- By using the **Server** value from objects passed through the pipeline
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

### -TargetPath
Specifies the new location for the object.
This location must be the path to a container or organizational unit.

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

### None or Microsoft.ActiveDirectory.Management.ADObject
An Active Directory object is received by the *Identity* parameter.

Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADOrganizationalUnit**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADObject
Returns the restored object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADObject](./Get-ADObject.md)

[Move-ADObject](./Move-ADObject.md)

[New-ADObject](./New-ADObject.md)

[Remove-ADObject](./Remove-ADObject.md)

[Rename-ADObject](./Rename-ADObject.md)

[Set-ADObject](./Set-ADObject.md)


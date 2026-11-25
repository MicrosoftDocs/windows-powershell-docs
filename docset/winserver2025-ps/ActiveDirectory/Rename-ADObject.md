---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/rename-adobject?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ADObject
---

# Rename-ADObject

## SYNOPSIS
Changes the name of an Active Directory object.

## SYNTAX

```
Rename-ADObject [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADObject> [-NewName] <String> [-Partition <String>] [-PassThru] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Rename-ADObject** cmdlet renames an Active Directory object.
This cmdlet sets the **Name** property of an Active Directory object that has a Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) of name.
To modify the given name, surname, and other name of a user, use the Set-ADUser cmdlet.
To modify the Security Account Manager (SAM) account name of a user, computer, or group, use the Set-ADUser, Set-ADComputer, or Set-ADGroup cmdlet.

The *Identity* parameter specifies the object to rename.
You can identify an object or container by its distinguished name or GUID.
You can also set the *Identity* parameter to an object variable such as `$<localObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADObject** cmdlet to get an object and then pass the object through the pipeline to the Rename-ADObject cmdlet.
You can also use the **Get-ADGroup**, **Get-ADUser**, **Get-ADComputer**, **Get-ADServiceAccount**, **Get-ADOrganizationalUnit**, and **Get-ADFineGrainedPasswordPolicy** cmdlets to get an object that you can pass through the pipeline to this cmdlet.

The *NewName* parameter defines the new name for the object and must be specified.

## EXAMPLES

### Example 1: Rename a site
```
PS C:\> Rename-ADObject -Identity "CN=HQ,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM" -NewName "UnitedKingdomHQ"
```

This command renames the name of an existing site HQ to the new name UnitedKingdomHQ.
If the distinguished name is provided in the *Identity* parameter, then the *Partition* parameter is not required.

### Example 2: Rename an object
```
PS C:\> Rename-ADObject -Identity "4777c8e8-cd29-4699-91e8-c507705a0966" -NewName "AmsterdamHQ" -Partition "CN=Configuration,DC=FABRIKAM,DC=COM"
```

This command renames the object with the GUID 4777c8e8-cd29-4699-91e8-c507705a0966 to SiteNewName.
The *Partition* parameter is required because the naming context of the site object is not known from the GUID specified by the *Identity* parameter.

### Example 3: Rename an object by distinguished name
```
PS C:\> Rename-ADObject -Identity "OU=ManagedGroups,OU=Managed,DC=Fabrikam,DC=Com" -NewName "Groups"
```

This command renames the object with the distinguished name OU=ManagedGroups,OU=Managed,DC=Fabrikam,DC=Com to Groups.

### Example 4: Rename an object by GUID
```
PS C:\> Rename-ADObject -Identity "4777c8e8-cd29-4699-91e8-c507705a0966" -NewName "DavidChew"
```

This command renames the object with GUID 4777c8e8-cd29-4699-91e8-c507705a0966 to DavidChews.
The *Partition* parameter is not specified because the object is in the default naming context of the domain.

### Example 5: Rename a container in an LDS instance
```
PS C:\> Rename-ADObject -Identity "CN=Apps,DC=AppNC" -NewName "InternalApps" -Server "FABRIKAM-SRV1:60000"
```

This command renames the container CN=Apps,DC=AppNC to InternalApps in an LDS instance.

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
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, the Active Directory module for Windows PowerShell returns a terminating error.

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
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following, are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

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
This parameter sets the Name property of the Active Directory object.
The LDAP display name (**ldapDisplayName**) of this property is name.

```yaml
Type: String
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
Note that rules listed first are evaluated first and when a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
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

### None or Microsoft.ActiveDirectory.Management.ADObject
An Active Directory object is received by the *Identity* parameter.

Derived types, such as the following, are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADOrganizationalUnit**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADObject](./Get-ADObject.md)

[Move-ADObject](./Move-ADObject.md)

[New-ADObject](./New-ADObject.md)

[Remove-ADObject](./Remove-ADObject.md)

[Restore-ADObject](./Restore-ADObject.md)

[Set-ADObject](./Set-ADObject.md)


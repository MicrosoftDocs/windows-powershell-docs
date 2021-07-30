---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/activedirectory/enable-adoptionalfeature?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ADOptionalFeature
---

# Enable-ADOptionalFeature

## SYNOPSIS
Enables an Active Directory optional feature.

## SYNTAX

```
Enable-ADOptionalFeature [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADOptionalFeature> [-PassThru] [-Scope] <ADOptionalFeatureScope> [-Server <String>]
 [-Target] <ADEntity> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-ADOptionalFeature** cmdlet enables an Active Directory optional feature that is associated with a particular domain mode or forest mode.
Active Directory optional features that depend on a specified domain mode or forest mode must be explicitly enabled after the domain mode or forest mode is set.

The **Identity** parameter specifies the Active Directory optional feature that you want to enable.
You can identify an optional feature by its distinguished name, feature GUID, or object GUID.
You can also set the parameter to an optional feature object variable, such as **$\<localOptionalFeatureObject\>** or you can pass an optional feature object through the pipeline to the **Identity** parameter.
For example, you can use the Get-ADOptionalFeature cmdlet to retrieve an optional feature object and then pass the object through the pipeline to the Enable-ADOptionalFeature cmdlet.

The **Scope** parameter specifies the scope at which the optional feature is enabled.

The **Target** parameter specifies the domain or forest on which the optional feature is enabled.
You can identify the domain or forest by its fully-qualified domain name (FQDN), NetBIOS name, or distinguished name of the domain naming context.

## EXAMPLES

### Example 1: Enable the Recycle Bin feature for a forest
```
PS C:\>Enable-ADOptionalFeature -Identity 'Recycle Bin Feature' -Scope ForestOrConfigurationSet -Target 'fabrikam.com' -Server dc1
```

This command enables the optional feature Recycle Bin feature for the forest fabrikam.com.
This operation must be performed on the domain controller that holds the naming flexible single master operations (FSMO) role.

### Example 2: Enable the Recycle bin for an AD LDS instance
```
PS C:\>Enable-ADOptionalFeature -Identity 'Feature 1' -Scope ForestOrConfigurationSet -Target 'CN=Configuration,CN={0241853A-6BBF-48AA-8AE0-9C35D0C91B7B}' -Server lds.fabrikam.com:50000
```

This command enables the optional feature Recycle Bin feature for the AD LDS instance lds.fabrikam.com.
This operation must be performed on the AD LDS instance that holds the naming FSMO role.

### Example 3: Set the ForestMode on an AD LDS instance
```
PS C:\>Set-ADObject -Identity "CN=Partitions,CN=Configuration,CN={4F971828-5BE4-4E94-B532-58F2BFB6A3A5}" -Replace @{"msDS-Behavior-Version"=4}
```

This command sets the **ForestMode** (Forest Functional Level) to Windows2008R2Forest on an AD LDS instance.
The **ForestMode** must be Windows2008R2Forest or later in order to enable the Recycle Bin feature for AD LDS.

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
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
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

You can also create a **PSCredential** object by using a script or by using the Get-Credentialhttps://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.
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
Specifies an Active Directory optional feature object by providing one of the following values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A FQDN
- A feature GUID (featureGUID)
- An object GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an optional feature object instance.

```yaml
Type: ADOptionalFeature
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Scope
Specifies the scope at which the feature is enabled or disabled.
The acceptable values for this parameter are:

- Domain or 0
- Forest or 1

```yaml
Type: ADOptionalFeatureScope
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, ForestOrConfigurationSet, Domain

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services (AD LDS), AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:  

 Domain name values:

- FQDN
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

### -Target
Specifies the domain or forest in which to modify the optional feature.
You can identify the target domain or forest by providing one of the following values: 

- FQDN of the forest or domain
- NetBIOS name of the forest or domain

You can also, where **Scope** is set to domain (not forest), use the following: 

- Distinguished name of the domain naming context

```yaml
Type: ADEntity
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADOptionalFeature
An optional feature object is received by the **Identity** parameter.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.
* Recycle Bin Feature: Once the Active Directory Recycle Bin is enabled, all objects deleted before the Active Directory Recycle Bin was enabled (tombstone objects) become recycled objects. They are no longer visible in the Deleted Objects container and they cannot be recovered using Active Directory Recycle Bin. The only way to restore these objects is through an authoritative restore from an AD DS backup taken before the Active Directory Recycle Bin was enabled.

## RELATED LINKS

[Disable-ADOptionalFeature](./Disable-ADOptionalFeature.md)

[Get-ADOptionalFeature](./Get-ADOptionalFeature.md)


---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 67C45D4A-2D6A-4AB9-A96E-B425558FAD11
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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
The Enable-ADOptionalFeature enables an Active Directory optional feature that is associated with a particular Domain mode or Forest mode.
Active Directory optional features that depend on a specified domain mode or Forest mode must be explicitly enabled after the domain mode or forest mode is set.

The Identity parameter specifies the Active Directory optional feature that you want to enable.
You can identify an optional feature by its distinguished name (DN), feature GUID, or object GUID.
You can also set the parameter to an optional feature object variable, such as $\<localOptionalFeatureObject\> or you can pass an optional feature object through the pipeline to the Identity parameter.
For example, you can use the Get-ADOptionalFeature cmdlet to retrieve an optional feature object and then pass the object through the pipeline to the Enable-ADOptionalFeature cmdlet.

The Scope parameter specifies the scope at which the optional feature will be enabled.
Possible values for this parameter are Domain and Forest.

The Target parameter specifies the domain or forest on which the optional feature will be enabled.
You can identify the domain or forest by its fully-qualified domain name (FQDN), NetBIOS name, or distinguished name (DN) of the domain naming context (domain NC).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Enable-ADOptionalFeature 'Recycle Bin Feature' -Scope ForestOrConfigurationSet -Target 'fabrikam.com' -Server dc1
```

Description

-----------

Enable the optional feature 'Recycle Bin Feature' for the forest 'fabrikam.com'. 
This operation must be performed on the Domain Controller that holds the naming master FSMO role.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Enable-ADOptionalFeature 'Recycle Bin Feature' -Scope ForestOrConfigurationSet -Target 'CN=Configuration,CN={0241853A-6BBF-48AA-8AE0-9C35D0C91B7B}' -Server lds.fabrikam.com:50000
```

Description

-----------

Enable the optional feature 'Recycle Bin Feature' for the AD LDS instance lds.fabrikam.com. 
This operation must be performed on the AD LDS instance that holds the naming master FSMO role.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
Possible values for this parameter include:

Negotiate or 0

Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

The following example shows how to set this parameter to Basic.

-AuthType Basic

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
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as "User1" or "Domain01\User01" or you can specify a PSCredential object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then set the Credential parameter to the PSCredential object The following example shows how to create credentials.

$AdminCredentials = Get-Credential "Domain01\User01"

The following shows how to set the Credential parameter to these credentials.

-Credential $AdminCredentials

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
Specifies an Active Directory optional feature object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.

Fully qualified domain name

Example: corp.contoso.com

Feature GUID (featureGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Object GUID (objectGUID)

Example: 482ab21c-823e-401e-879a-ac7383d64eb9

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an optional feature object instance.

This example shows how to set the parameter to a fully qualified domain name.

-Identity "corp.contoso.com"

This example shows how to set this parameter to an optional feature object instance named "optionalFeatureInstance".

-Identity $optionalFeatureInstance

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
Returns the new or modified object.
By default (i.e.
if -PassThru is not specified), this cmdlet does not generate any output.

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
Possible values for this parameter include:

Domain or 0

Forest or 1

The following example shows how to set this parameter so that optional features are enabled or disabled within the scope of the forest.

-Scope Forest

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
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

Fully qualified domain name

Examples: corp.contoso.com

NetBIOS name

Example: CORP

Directory server values:

Fully qualified directory server name

Example: corp-DC12.corp.contoso.com

NetBIOS name

Example: corp-DC12

Fully qualified directory server name and port

Example: corp-DC12.corp.contoso.com:3268

The default value for the Server parameter is determined by one of the following methods in the order that they are listed:

-By using Server value from objects passed through the pipeline.

-By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.

-By using the domain of the computer running Windows PowerShell.

The following example shows how to specify a full qualified domain name as the parameter value.

-Server "corp.contoso.com"

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

Fully-qualified domain name of the forest or domain

Example: corp.Fabrikam.com

NetBIOS name of the forest or domain

Example: corp

You can also where Scope is set to domain (not forest), use the following:

Distinguished name (DN) of the domain naming context (domain NC)

Example:  DC=corp,DC=Fabrikam,DC=com

The following example shows how to set this parameter using a DN to a domain NC when the scope of the command is set to forest level.

-Target "DC=corp,DC=Fabrikam,DC=com"

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADOptionalFeature
An optional feature object is received by the Identity parameter.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

  Recycle Bin Feature: Once the Active Directory Recycle Bin is enabled, all objects deleted before the Active Directory Recycle Bin was enabled (tombstone objects) become recycled objects.
They are no longer visible in the Deleted Objects container and they cannot be recovered using Active Directory Recycle Bin. 
The only way to restore these objects is though an authoritative restore from an AD DS backup taken before the Active Directory Recycle Bin was enabled.

## RELATED LINKS

[Disable-ADOptionalFeature](./Disable-ADOptionalFeature.md)

[Get-ADOptionalFeature](./Get-ADOptionalFeature.md)


---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 51EE4E28-C6FF-4AF9-856C-6B517B3353BF
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-ADForestMode

## SYNOPSIS
Sets the forest mode for an Active Directory forest.

## SYNTAX

```
Set-ADForestMode [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-ForestMode] <ADForestMode> [-Identity] <ADForest> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADForestMode cmdlet sets the Forest mode for an Active Directory forest.
You specify the forest mode by setting the ForestMode parameter.
The forest mode can be set to the following values that are listed in order of functionality from lowest to highest.

Windows2000Forest

Windows2003InterimForest

Windows2003Forest

Windows2008Forest

Windows2008R2Forest

The Identity parameter specifies the Active Directory forest to modify.
You can identify a forest by its fully qualified domain name (FQDN), GUID, DNS host name, or NetBIOS name.
You can also specify the forest by passing a forest object through the pipeline.
For example, you can use the Get-ADForest cmdlet to retrieve a forest object and then pass the object through the pipeline to the Set-ADForestMode.

Set-ADForestMode will prompt for confirmation by default.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADForestMode -Identity fabrikam.com -ForestMode Windows2003Forest
```

Description

-----------

Set the ForestMode to Windows2003Forest in the forest fabrikam.com.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>$currentForest = Get-ADForest
Set-ADForestMode -Identity $currentForest -Server $currentForest.SchemaMaster -ForestMode Windows2008R2Forest
```

Description

-----------

Set the forest mode of the current logged on user's forest.
The Set operation targets the Schema Master FSMO to apply the update.

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

### -ForestMode
Specifies the forest mode for an Active Directory forest.
The possible values for this parameter are:   Windows2000Forest or 0

Windows2003InterimForest or 1

Windows2003Forest or 2

Windows2008Forest or 3

Windows2008R2Forest or 4

The values are listed in order of functionality from least to most.

The following example shows how to set this parameter.

-ForestMode Windows2008R2Forest

```yaml
Type: ADForestMode
Parameter Sets: (All)
Aliases: 
Accepted values: Windows2000Forest, Windows2003InterimForest, Windows2003Forest, Windows2008Forest, Windows2008R2Forest, Windows2012Forest, UnknownForest

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory forest object by providing one of the following attribute values.
The identifier in parentheses is the LDAP display name for the attribute.

Fully qualified domain name

Example: corp.contoso.com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

DNS host name

Example: dnsServer.corp.contoso.com

NetBIOS name

Example: corp

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a forest object instance.

This example shows how to set the parameter to a fully qualified domain name.

-Identity "corp.contoso.com"

This example shows how to set this parameter to a forest object instance named "forestInstance".

-Identity $forestInstance

```yaml
Type: ADForest
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

-By using the domain of the computer running Powershell.

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

### None or Microsoft.ActiveDirectory.Management.ADForest
A forest object is received by the Identity parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADForest
Returns the modified forest object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller

## RELATED LINKS

[Get-ADForest](./Get-ADForest.md)


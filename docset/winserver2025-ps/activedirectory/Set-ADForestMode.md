---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 04/11/2024
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adforestmode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADForestMode
---

# Set-ADForestMode

## SYNOPSIS
Sets the forest mode for an Active Directory forest.

## SYNTAX

```
Set-ADForestMode [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-ForestMode] <ADForestMode> [-Identity] <ADForest> [-PassThru] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-ADForestMode` cmdlet sets the forest mode for an Active Directory forest. You specify the
forest mode by setting the **ForestMode** parameter.

The **Identity** parameter specifies the Active Directory forest to modify. You can identify a
forest by its fully qualified domain name (FQDN), GUID, DNS host name, or NetBIOS name. You can
also specify the forest by passing a forest object through the pipeline. For example, you can use
the `Get-ADForest` cmdlet to retrieve a forest object and then pass the object through the
pipeline to the `Set-ADForestMode` cmdlet.

`Set-ADForestMode` prompts for confirmation by default.

## EXAMPLES

### Example 1: Set the forest mode for a forest

```powershell
Set-ADForestMode -Identity fabrikam.com -ForestMode Windows2003Forest
```

This command sets the **ForestMode** to `Windows2003Forest` in the forest `fabrikam.com`.

### Example 2: Set the forest mode for the current user

```powershell
$params = @{
    Identity = (Get-ADForest)
    Server = $params.Identity.SchemaMaster
    ForestMode = 'Windows2008R2Forest'
}
Set-ADForestMode @params
```

This example sets the forest mode of the current user's forest. The set operation targets the
schema master flexible single master operation (FSMO) role to apply the update.

## PARAMETERS

### -AuthType

Specifies the authentication method to use. The acceptable values for this parameter are:

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

Specifies the user account credentials to use to perform this task. The default credentials are the
credentials of the currently logged on user unless the cmdlet is run from an Active Directory
module for Windows PowerShell provider drive. If the cmdlet is run from such a provider drive, the
account associated with the drive is the default.

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you
can specify a **PSCredential** object. If you specify a user name for this parameter, the cmdlet
prompts for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the **Credential** parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active
Directory module for Windows PowerShell returns a terminating error.

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

Specifies the forest mode for an Active Directory forest. The acceptable values for this parameter
are:

- Windows2000Forest or 0
- Windows2003InterimForest or 1
- Windows2003Forest or 2
- Windows2008Forest or 3
- Windows2008R2Forest or 4
- Windows2012Forest or 5
- Windows2012R2Forest or 6
- Windows2016Forest or 7
- Windows2025Forest or 10

The values are listed in order of functionality from least to most.

```yaml
Type: ADForestMode
Parameter Sets: (All)
Aliases:
Accepted values: Windows2000Forest, Windows2003InterimForest, Windows2003Forest, Windows2008Forest, Windows2008R2Forest, Windows2012Forest, Windows2012R2Forest, Windows2016Forest, Windows2025Forest, UnknownForest

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies an Active Directory forest object by providing one of the following attribute values. The
identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the
attribute. The acceptable values for this parameter are:

- A fully qualified domain name
- A GUID (objectGUID)
- A DNS host name
- A NetBIOS name

The cmdlet searches the default naming context or partition to find the object. If two or more
objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a
forest object instance.

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

Returns an object representing the item with which you are working. By default, this cmdlet does
not generate any output.

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

Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of
the following values for a corresponding domain name or directory server. The service may be any of
the following:

- Active Directory Lightweight Directory Services (AD LDS)
- AD DS
- Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order
that they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the AD DS Windows PowerShell provider drive, when
  the cmdlet runs in that drive
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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADForest

You can pipe a forest object to the **Identity** parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADForest

This cmdlet returns the modified forest object when the **PassThru** parameter is specified. By
default, this cmdlet does not generate any output.

## NOTES

- This cmdlet does not work with AD LDS.
- This cmdlet does not work with an Active Directory snapshot.
- This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADForest](Get-ADForest.md)

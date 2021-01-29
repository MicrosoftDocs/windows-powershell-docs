---
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Export-AdfsDeploymentSQLScript
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: DA4481D6-DBE1-4E28-8D2A-F1A1ECC75C29
---

# Export-AdfsDeploymentSQLScript

## SYNOPSIS
Generates SQL scripts to create the AD FS database and to grant permissions.

## SYNTAX

```
Export-AdfsDeploymentSQLScript -DestinationFolder <String> -ServiceAccountName <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-AdfsDeploymentSQLScript** cmdlet generates the SQL scripts that you can use separately to create the Active Directory Federation Services (AD FS) database and to grant permissions.

## EXAMPLES

### Example 1: Export SQL deployment scripts
```
PS C:\> Export-AdfsDeploymentSQLScript -DestinationFolder ".\ScriptFolder" -ServiceAccountName "ContosoDomain\AdfsUser"
```

This command exports SQL deployment scripts for AD FS installation on behalf of the specified AD FS service account.

## PARAMETERS

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

### -DestinationFolder
Specifies the folder in which the cmdlet saves the generated SQL scripts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccountName
Specifies the name of the Active Directory® Domain Services account under which the AD FS service runs. 
All nodes in the farm must use the same service account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

## OUTPUTS

## NOTES

## RELATED LINKS


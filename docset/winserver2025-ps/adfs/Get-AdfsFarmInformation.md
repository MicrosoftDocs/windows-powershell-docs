---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsfarminformation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsFarmInformation
---

# Get-AdfsFarmInformation

## SYNOPSIS
Gets AD FS behavior level and farm node information.

## SYNTAX

```
Get-AdfsFarmInformation [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsFarmInformation** cmdlet gets the current Active Directory Federation Services (AD FS) behavior level and farm node information.

## EXAMPLES

### Example 1: Get farm information
```
PS C:\> Get-AdfsFarmInformation
```

This cmdlet gets AD FS behavior level and farm node information.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AdfsFarmInformation](./Set-AdfsFarmInformation.md)


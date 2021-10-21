---
description: Gets the properties for an AD FS threat detection module.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 10/01/2021
online version: https://docs.microsoft.com/powershell/module/adfs/get-adfsthreatdetectionmodule?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsThreatDetectionModule
---

# Get-AdfsThreatDetectionModule

## SYNOPSIS
Gets the properties for an AD FS threat detection module.

## SYNTAX

```
Get-AdfsThreatDetectionModule [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION

The **Get-AdfsThreatDetectionModule** cmdlet gets the properties for an AD FS threat detection
module.

## EXAMPLES

### Example 1: Get the properties of an AD FS module
```powershell
PS> Get-AdfsThreatDetectionModule -Name "IPBlockPlugin"
```

Gets the properties an AD FS module named `IPBlockPlugin`.

## PARAMETERS

### -Name
Specifies the friendly name.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

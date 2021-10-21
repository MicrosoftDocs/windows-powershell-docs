---
description: Unregisters an AD FS threat detection module.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 10/20/2021
online version: https://docs.microsoft.com/powershell/module/adfs/unregister-adfsthreatdetectionmodule?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-AdfsThreatDetectionModule
---

# Unregister-AdfsThreatDetectionModule

## SYNOPSIS
Unregisters an AD FS threat detection module.

## SYNTAX

```
Unregister-AdfsThreatDetectionModule [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-AdfsThreatDetectionModule** cmdlet unregisters an AD FS module.

For more information, see
[Build Plug-ins with AD FS 2019 Risk Assessment Model](/windows-server/identity/ad-fs/development/ad-fs-risk-assessment-model).

## EXAMPLES

### Example 1: Unregister an AD FS threat detection module
```powershell
PS> Unregister-AdfsThreatDetectionModule -Name "IPBlockPlugin"
```

Unregisters an AD FS threat detection module `IPBlockPlugin`.

## PARAMETERS

### -Name
Specifies the friendly name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

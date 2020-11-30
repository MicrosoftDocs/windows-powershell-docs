---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: DCDD5CDF-2A20-4C18-BA41-BE8B81AC07A8
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-MbamCMIntegration
ms.reviewer:
---

# Disable-MbamCMIntegration

## SYNOPSIS
Disables the MBAM Microsoft Endpoint Configuration Manager Integration feature.

## SYNTAX

```
Disable-MbamCMIntegration [-Force] [-RemoveComplianceData] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-MbamCMIntegration** cmdlet disables the Microsoft BitLocker Administration and Monitoring (MBAM) Microsoft Endpoint Configuration Manager Integration feature.

## EXAMPLES

### Example 1: Disable the Microsoft Endpoint Configuration Manager Integration feature
```
PS C:\> Disable-MbamCMIntegration
Are you sure you want to perform this action?
Performing operation "Disable MBAM CM Integration feature"
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command disables the MBAM Microsoft Endpoint Configuration Manager Integration feature after you confirm the operation.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet performs the operation without prompting you for confirmation.

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

### -RemoveComplianceData
Indicates that this cmdlet removes compliance data, as well as reports, from Configuration Manager.
If you do not specify this parameter, this cmdlet only removes the Configuration Manager reports.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-MbamCMIntegration](enable-mbamcmintegration.md)

[Get-MbamCMIntegration](get-mbamcmintegration.md)

[Test-MbamCMIntegration](test-mbamcmintegration.md)



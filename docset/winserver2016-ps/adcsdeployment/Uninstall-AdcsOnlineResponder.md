---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Uninstall-AdcsOnlineResponder
ms.reviewer:
ms.assetid: DB15EC96-69EF-4303-BD9B-254619C02C4C
---

# Uninstall-AdcsOnlineResponder

## SYNOPSIS
Uninstalls the Online Responder service.

## SYNTAX

```
Uninstall-AdcsOnlineResponder [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-AdcsOnlineResponder** cmdlet uninstalls the Online Responder role service.

## EXAMPLES

### Example 1: Uninstall the Online Responder role service
```
PS C:\> Uninstall-AdcsOnlineResponder -Force
```

This command removes Online Responder role service without requiring confirmation.

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
Forces the command to run without asking for user confirmation.

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

### None

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.OCSP.OnlineResponderResult

## NOTES
* Ensure you run Windows PowerShell as an administrator. You can use the *Force* parameter to bypass the prompt for confirmation.

  

## RELATED LINKS

[Install-AdcsOnlineResponder](./Install-AdcsOnlineResponder.md)


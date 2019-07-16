---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Uninstall-AdcsNetworkDeviceEnrollmentService
ms.reviewer:
ms.assetid: BD14AF56-FE90-4C77-BA1C-27DC49E11FA1
---

# Uninstall-AdcsNetworkDeviceEnrollmentService

## SYNOPSIS
Uninstalls the NDES role service.

## SYNTAX

```
Uninstall-AdcsNetworkDeviceEnrollmentService [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-AdcsNetworkDeviceEnrollmentService** cmdlet uninstalls the Network Device Enrollment Service (NDES) role service.

## EXAMPLES

### Example 1: Uninstall the NDES role service
```
PS C:\> Uninstall-AdcsNetworkDeviceEnrollmentService -Force
```

This command uninstalls the NDES role service and does not prompt for user input.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.NDES.NetworkDeviceEnrollmentServiceResult

## NOTES
* Ensure you run Windows PowerShell as an administrator. You can use the *Force* parameter to bypass the prompt for confirmation.

  

## RELATED LINKS

[Install-AdcsNetworkDeviceEnrollmentService](./Install-AdcsNetworkDeviceEnrollmentService.md)


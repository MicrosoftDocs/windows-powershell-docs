---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Uninstall-DeviceHealthAttestation
ms.reviewer:
ms.assetid: D84D2048-B990-47B6-B237-51084039D42A
---

# Uninstall-DeviceHealthAttestation

## SYNOPSIS
Uninstalls the Device Health Attestation service.

## SYNTAX

```
Uninstall-DeviceHealthAttestation [-RemoveSslBinding] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-DeviceHealthAttestation** cmdlet uninstalls the Device Health Attestation service and its dependencies.
The cmdlet also removes the firewall rule for incoming requests, the web application, and the application pool.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Uninstall the Device Health Attestation service
```
PS C:\> Uninstall-DeviceHealthAttestation
```

This command uninstalls the Device Health Attestation service.

### Example 2: Uninstall the Device Health Attestation service with SSL bindings
```
PS C:\> Uninstall-DeviceHealthAttestation -RemoveSslBinding
```

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

### -RemoveSslBinding
Removes the SSL binding from the default website.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Install-DeviceHealthAttestation](./Install-DeviceHealthAttestation.md)


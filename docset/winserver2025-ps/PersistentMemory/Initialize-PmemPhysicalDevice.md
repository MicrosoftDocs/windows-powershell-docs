---
description: The Initialize-PmemPhysicalDevice cmdlet initializes the label storage area on a physical persistent memory device.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/initialize-pmemphysicaldevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-PmemPhysicalDevice
---

# Initialize-PmemPhysicalDevice

## SYNOPSIS
Initializes the label storage area on a physical persistent memory device.

## SYNTAX

```
Initialize-PmemPhysicalDevice -DeviceId <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-PmemPhysicalDevice** cmdlet initializes the label storage area on a physical persistent memory device.

Each persistent memory module contains a label storage area that stores configuration metadata.
The cmdlet can clear corrupted label storage information on the devices.

This cmdlet causes data loss in persistent memory.
Use it only as a last resort to fix persistent memory issues.

## EXAMPLES

### Example 1: Initialize physical devices
```powershell
Get-PmemPhysicalDevice | Initialize-PmemPhysicalDevice
```

```output
This will initialize the label storage area on the physical persistent memory device(s) and will result in data loss.
Initializes the physical persistent memory device(s)?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
Initializing the physical persistent memory device. This may take a few moments.
Initializing the physical persistent memory device. This may take a few moments.
Initializing the physical persistent memory device. This may take a few moments.
Initializing the physical persistent memory device. This may take a few moments.
```

This command initializes the label storage areas on the physical persistent memory devices.
The command can clear corrupted label storage information on the devices.

## PARAMETERS

### -DeviceId
Specifies the device ID of the device to initialize.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force
Indicates that the command initializes the device without verification.
Removing a disk results in data loss.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-PmemPhysicalDevice](Get-PmemPhysicalDevice.md)

[New-PmemDisk](New-PmemDisk.md)

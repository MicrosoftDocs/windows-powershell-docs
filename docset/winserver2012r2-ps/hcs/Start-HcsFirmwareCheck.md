---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Start-HcsFirmwareCheck
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 531578FE-23E6-4F87-80E2-8E3CE4EF402E
---

# Start-HcsFirmwareCheck

## SYNOPSIS
Checks whether a device needs a firmware update.

## SYNTAX

```
Start-HcsFirmwareCheck [-Force] [-ClearUSMUpgradeCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-HcsFirmwareCheck** cmdlet checks whether a device needs a firmware update.
The cmdlet automatically updates any firmware that it can update to the latest known firmware.
This cmdlet lists all firmware that it cannot update.
Contact Microsoft Customer Service and Support about any firmware that this cmdlet cannot update.

This cmdlet runs automatically as a scheduled task on the active controller once a day, but you can also run the cmdlet on an as-needed basis.

## EXAMPLES

### Example 1: Start a firmware check
```
PS C:\>Start-HcsFirmwareCheck
FirmwareStatus     : UpToDate
MismatchComponents :
```

This command checks the firmware version of a device.
The firmware on this device is up to date.

### Example 2: Update firmware
```
PS C:\>Start-HcsFirmwareCheck

Confirm

The firmware on the device is not up to date. This operation starts a firmware 
update installation run and could reboot one or both of the controllers. If the 
device is serving I/Os they will not be disrupted.  Are you sure you want to 
proceed? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command checks the firmware version of a device.
The firmware on this device is not up to date.
This command does not specify the **Force** parameter, and, therefore, the cmdlet prompts you for confirmation before it updates the firmware.

### Example 3: Check for firmware updates that require support
```
PS C:\>Start-HcsFirmwareCheck

FirmwareStatus     : SupportRequired
MismatchComponents : BmcRoot
                                                  BmcBoot
```

This command checks the firmware version of a device.
The firmware on this device is not up to date.
The cmdlet cannot update some firmware for this device.
Contact Customer Service and Support in order to update this item.

## PARAMETERS

### -ClearUSMUpgradeCheck
{{Fill ClearUSMUpgradeCheck Description}}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Patching.HcsFirmwareCheckResult
The HcsFirmwareCheckResult object has the following properties:

- FirmwareStatus FirmwareStatus 
- IEnumerable\<String\> MismatchComponents

The FirmwareStatus enumeration has the following values:

- UpToDate
- SupportRequired
- MaintenanceModeUpdateRequired
- UpdateStarted
- UpdateRequired

## NOTES

## RELATED LINKS

[Get-HcsFirmwareVersion](./Get-HcsFirmwareVersion.md)


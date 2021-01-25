---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Start-HcsUpdate
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 82A1E141-1494-46C5-B1AC-A772943BF1E4
---

# Start-HcsUpdate

## SYNOPSIS
Installs updates.

## SYNTAX

```
Start-HcsUpdate [-Force] [-UpdateId <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-HcsUpdate** cmdlet installs updates on a device.
If the device is in maintenance mode, the cmdlet installs only disruptive updates.
If the device is not in maintenance mode, the cmdlet installs only normal updates.

For updates that do not require maintenance mode, this cmdlet installs the update on both controllers.

For all updates that require maintenance mode, run this cmdlet on each controller.
If you do not to run this cmdlet on each controller, data may become corrupted.

## EXAMPLES

### Example 1: Install updates
```
PS C:\>Start-HcsUpdate
```

This command installs available updates.

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

### -UpdateId
Specifies an update ID.
The cmdlet installs the particular update specified by the ID.

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

### Boolean
This cmdlet generates a value of $True if it starts installing an update or a value of $False if there are no updates available.

## NOTES

## RELATED LINKS

[Get-HcsUpdateAvailability](./Get-HcsUpdateAvailability.md)

[Get-HcsUpdateStatus](./Get-HcsUpdateStatus.md)

[Start-HcsHotfix](./Start-HcsHotfix.md)


---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Enter-HcsMaintenanceMode
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 36D665B9-F57E-4924-BFBD-DEF9C90751AA
---

# Enter-HcsMaintenanceMode

## SYNOPSIS
Puts a device into maintenance mode.

## SYNTAX

```
Enter-HcsMaintenanceMode [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Enter-HcsMaintenanceMode** cmdlet puts a device into maintenance mode.
Putting a device in maintenance mode disrupts its I/Os and severs its connection to the azure_1 Management Portal.
Maintenance mode is primarily for installing updates that require you to disable I/O.
Updates to disk firmware require you to disable I/O.

## EXAMPLES

### Example 1: Enter device maintenance mode
```
PS C:\> Enter-HcsMaintenanceMode


Maintenance mode will disrupt all IOs and server the connection to the 
azure_1 Management Portal. Entering maintenance mode will reboot both 
controllers, which takes a few minutes to complete. Are you sure you want to enter 
maintenance mode? 
[Y] Yes  [N] No  [?] Help (default is "Y"):
----------------MAINTENANCE MODE-----------------

azure_1 StorSimple Device Model 7700
Name: emards_device
Software Version: 6.3.9600.16517
Copyright (C) 2013 Microsoft Corporation. All rights reserved. 
You are connected to Controller1

-------------------------------------------------
```

This command enters device maintenance mode.

To reconnect, you must start a new Windows PowerShell® session.
When you reconnect, maintenance mode information is displayed.

## PARAMETERS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Exit-HcsMaintenanceMode](./Exit-HcsMaintenanceMode.md)

[Get-HcsFirmwareVersion](./Get-HcsFirmwareVersion.md)

[Start-HcsFirmwareCheck](./Start-HcsFirmwareCheck.md)


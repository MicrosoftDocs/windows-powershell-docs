---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/hcs/exit-hcsmaintenancemode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-HcsMaintenanceMode
---

# Exit-HcsMaintenanceMode

## SYNOPSIS
Takes a device out of maintenance mode.

## SYNTAX

```
Exit-HcsMaintenanceMode [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Exit-HcsMaintenanceMode** cmdlet takes a device out of maintenance mode.
Taking a device out of maintenance mode restores I/Os and restores the connection to the azure_1 Management Portal.

Before exiting maintenance mode, ensure that all updates are fully installed on all controllers.
You must install maintenance mode updates on each controller individually.
If you do not install these updates on each controller before the device enters maintenance mode, data may become corrupted.

## EXAMPLES

### Example 1: Exiting maintenance mode
```
PS C:\> Exit-HcsMaintenanceMode


Before exiting maintenance mode, ensure that any updates that are required on both 
controllers have been applied. Failure to install on each controller could result
in data corruption. Exiting maintenance mode will reboot both controllers, which 
takes a few minutes to complete. Are you sure you want to exit maintenance mode?
[Y] Yes  [N] No  [?] Help (default is "Y"): y
```

This command exits maintenance mode.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
No return value.

## NOTES

## RELATED LINKS

[Enter-HcsMaintenanceMode](./Enter-HcsMaintenanceMode.md)


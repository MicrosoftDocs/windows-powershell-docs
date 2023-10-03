---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/hcs/get-hcsfirmwareversion?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HcsFirmwareVersion
---

# Get-HcsFirmwareVersion

## SYNOPSIS
Gets the firmware versions of devices and displays the results.

## SYNTAX

```
Get-HcsFirmwareVersion [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsFirmwareVersion** cmdlet gets the firmware versions of devices and displays the results.

This cmdlet runs automatically as a scheduled task on the active controller once a day, but you can also run the cmdlet as needed.

## EXAMPLES

### Example 1: Get the firmware version
```
PS C:\>Get-HcsFirmwareVersion
```

This command gets the firmware version of a device and displays the results.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Patching.HcsFirmwareVersion
The HcsFirmwareVersion object has the following properties: 

- NodeFirmwareVersion Controller 0 
- NodeFirmwareVersion Controller 1

The NodeFirmwareVersion object has the following properties:

- TalladegaFirmware TalladegaController 
- EbodFirmware EbodController
- DisksFirmware DisksFirmware

## NOTES

## RELATED LINKS

[Start-HcsFirmwareCheck](./Start-HcsFirmwareCheck.md)


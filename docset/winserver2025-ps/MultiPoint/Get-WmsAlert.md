---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/get-wmsalert?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsAlert
---

# Get-WmsAlert

## SYNOPSIS
Gets alert information.

## SYNTAX

```
Get-WmsAlert [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsAlert** cmdlet gets alert information from the Windows MultiPoint Server core service.

## EXAMPLES

### Example 1: Get alert information
```
PS C:\> Get-WmsAlert
TimeStampInUtc : 12/7/2010 12:17:15 AM
AlertType      : HubMissingRequiredDevice
AlertSeverity  : Warning
ComputerName   : TEST
StationId      : 1
```

This cmdlet returns alert information from the MultiPoint Server core service.
In this example, station 1 is missing a keyboard.

## PARAMETERS

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.WmsAlert

## NOTES

## RELATED LINKS


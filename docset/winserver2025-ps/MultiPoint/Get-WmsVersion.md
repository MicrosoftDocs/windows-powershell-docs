---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/get-wmsversion?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsVersion
---

# Get-WmsVersion

## SYNOPSIS
Gets the server version, the Connector version, and the SKU.

## SYNTAX

```
Get-WmsVersion [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsVersion** cmdlet gets the MultiPoint Server version, the MultiPoint Connector version, and the MultiPoint SKU.

## EXAMPLES

### Example 1: Get the MultiPoint version
```
PS C:\> Get-WmsVersion
ServerVersion                 ClientVersion                         SKU     ProtocolVersion
-------------                 -------------                         ---     ---------------
10.0.10586.0                  10.0.10586.0                          77      1
```

This command gets the version information for the current computer.

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

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.WmsVersion

## NOTES

## RELATED LINKS


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/set-winhomelocation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WinHomeLocation
---

# Set-WinHomeLocation

## SYNOPSIS
Sets the home location setting for the current user account.

## SYNTAX

```
Set-WinHomeLocation [-GeoId] <Int32> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinHomeLocation** cmdlet sets the value of the user **GeoID** object.
The Windows GeoID setting is a user setting that describes the home location of the current user account.
A home location is the country or region.
Applications that require the home location of the current user account, such as a driver for a television tuner application, can use this setting.

For a table of GeoIDs, see Table of [Geographical Locations](https://go.microsoft.com/fwlink/?LinkID=242308).

## EXAMPLES

### Example 1: Set the home location
```
PS C:\> Set-WinHomeLocation -GeoId 0xF4
```

This command sets the home location for the current user account to 0xF4 (hex) (United States).

## PARAMETERS

### -GeoId
Specifies a GeoID setting.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[RegionInfo.GeoId Property](https://go.microsoft.com/fwlink/?LinkID=242310)

[Get-WinHomeLocation](./Get-WinHomeLocation.md)


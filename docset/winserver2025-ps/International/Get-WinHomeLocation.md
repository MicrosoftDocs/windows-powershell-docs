---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/get-winhomelocation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinHomeLocation
---

# Get-WinHomeLocation

## SYNOPSIS
Gets the Windows GeoID home location setting for the current user account.

## SYNTAX

```
Get-WinHomeLocation [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinHomeLocation** cmdlet gets the value of the user GeoID setting and returns a .NET GeoID object.
The Windows GeoID setting is a user setting that describes the home location of the current user account.
A home location is the country or region.
Applications that require the home location of the current user account, such as a driver for a television tuner application, can use this setting.

For a table of GeoIDs, see Table of [Geographical Locations](https://go.microsoft.com/fwlink/?LinkID=242308).

## EXAMPLES

### Example 1: Display the GeoID for the current account
```
PS C:\> Get-WinHomeLocation
HomeLocation     Description
----             -----------
244              United States
```

This command returns the GeoID setting and its display name for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### GeoID
This cmdlet returns a 32-bit signed number that uniquely identifies a geographical location.

## NOTES

## RELATED LINKS

[RegionInfo.GeoId Property](https://go.microsoft.com/fwlink/?LinkID=242310)

[Set-WinHomeLocation](./Set-WinHomeLocation.md)


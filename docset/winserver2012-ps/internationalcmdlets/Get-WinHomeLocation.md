---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: 669C0C9E-37E4-474C-BC4C-465AE06EAFA3
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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
The Windows GeoID setting is a user setting that describes the home location (that is, the country or region) of the current user account.
Applications that require the current user account's home location, such as a driver for a television tuner application, can use this setting.

A table of GeoIDs is available at Table of Geographical Locationshttp://go.microsoft.com/fwlink/?LinkID=242308 (http://go.microsoft.com/fwlink/?LinkID=242308).

## EXAMPLES

### Example 1: Get the GeoID setting
```
PS C:\>Get-WinHomeLocation
HomeLocation     Description

----             -----------

244              United States
```

This command returns the GeoID setting and its display name for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### GeoID
A 32-bit signed number that uniquely identifies a geographical location.

## NOTES

## RELATED LINKS

[RegionInfo.GeoId Property](https://go.microsoft.com/fwlink/?LinkID=242310)


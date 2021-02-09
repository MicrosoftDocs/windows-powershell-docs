---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Get-WinHomeLocation
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 63F83180-AE7C-47ED-9099-9D46D00E2650
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

A table of GeoIDs is available at Table of Geographical Locationshttp://go.microsoft.com/fwlink/?LinkID=242308.

## EXAMPLES

### Example 1
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

[Set-WinHomeLocation](./Set-WinHomeLocation.md)


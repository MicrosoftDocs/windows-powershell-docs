---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: C58C14B2-CA4A-481D-AFC7-7D63BF33BF73
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-WinHomeLocation

## SYNOPSIS
Sets the home location setting for the current user account.

## SYNTAX

```
Set-WinHomeLocation [-GeoId] <Int32> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinHomeLocation** cmdlet sets the value of the user GeoID object.
The Windows GeoID setting is a user setting that describes the home location (that is, the country or region) of the current user account.
Applications that require the current user account's home location, such as a driver for a television tuner application, can use this setting.

A table of GeoIDs is available at Table of Geographical Locationshttp://go.microsoft.com/fwlink/?LinkID=242308.

## EXAMPLES

### Example 1: Set the home location for the current user
```
PS C:\>Set-WinHomeLocation -GeoID 0xF4
```

This command sets the home location for the current user account to 0xF4 (hex) (United States).

## PARAMETERS

### -GeoId
Specifies a 32-bit signed number that uniquely identifies a geographical location.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[RegionInfo.GeoId Property](https://go.microsoft.com/fwlink/?LinkID=242310)



---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: erik0686
author: Erik Torres
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: aandrejs
ms.date: 10/23/2020
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.1.0
title: Copy-UserInternationalSettingsToSystem
ms.reviewer:
ms.assetid: 
---

# Copy-UserInternationalSettingsToSystem

## SYNOPSIS
Copies the current user's international settings (Windows Display language, Input language, Regional Format/locale and Location/GeoID) to one or both of the following:
    * Welcome screen and system accounts
    * New user accounts

This is a system setting. It can only be changed by a user who has Administrator permissions. Changes take effect after the computer is restarted.

## SYNTAX

```
Copy-UserInternationalSettingsToSystem [-WelcomeScreen <Boolean>] [-NewUser <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-UserInternationalSettingsToSystem** cmdlet gets the **international settings** from the current user.
You can decide whether to copy these settings into the **Welcome screen and system accounts**, the **New user accounts** or both.

This cmdlet needs two parameters: **-WelcomeScreen** and **-NewUser**.

When any of the parameters is set to $True, this gets the current values from the current user and copies them to the system settings for the selected options based on the parameters that were set to $True.


## EXAMPLES

### Example 1: Copy settings into both the Welcome screen and new user accounts
```
PS C:\> Copy-UserInternationalSettingsToSystem -WelcomeScreen $True -NewUser $True
```

This example copies the Windows Display language, Input language, Regional Format/locale and Location/GeoID into both the Welcome screen and the new user accounts.


### Example 2: Copy the settings into only the Welcome screen
```
PS C:\> Copy-UserInternationalSettingsToSystem -WelcomeScreen $True -NewUser $False
```

This example copies the Windows Display language, Input language, Format/locale and Regional Location/GeoID to the Welcome screen only.


## PARAMETERS

### -WelcomeScreen
Copies the settings into the Welcome Screen and System accounts.

```yaml
Type: Boolean
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewUser
Copies the settings into the new user accounts.

```yaml
Type: Boolean
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).
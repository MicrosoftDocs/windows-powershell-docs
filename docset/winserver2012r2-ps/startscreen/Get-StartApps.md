---
external help file: Microsoft.Windows.StartScreen.Commands.dll-help.xml
Module Name: StartScreen
online version: 
schema: 2.0.0
title: Get-StartApps
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A0DC75B1-0BAB-4642-B9D2-FFD135355966
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-StartApps

## SYNOPSIS
Gets the names and AppIDs of apps in the Start screen.

## SYNTAX

```
Get-StartApps [[-Name] <Object>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StartApps** cmdlet gets the names and AppIDs of apps in the Start screen of the current user.
An AppID is an AppUserModelID.
You can specify a particular app by using its name, or you can specify a name that includes the wildcard character (*).
If you do not specify a name, the cmdlet displays all the apps from the Start screen.

## EXAMPLES

### Example 1: Get all apps on the Start screen
```
PS C:\> Get-StartApps
Name AppID
---- -----

A. Datum Pro Center Datum.ProCenter
Proseware Studio Proseware.Studio.5
A. Datum 2010 prog..tion_0000000000000000_ebec13db489e8ef9
Fabrikam Initializer Fabrikam.Initializer.1
A. Datum Connector Contoso.Datum.Connector
Proseware Design Pro Proseware.Design.3
```

This command gets all the names and IDs of apps in the Start screen for the current user.

## PARAMETERS

### -Name
Specifies the name of an app.
You can use the wildcard character.
If you do not specify this parameter, the cmdlet gets all the apps.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: All Apps
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSObject
A **PSObject** that contains the name and AppID for each app found in the Start screen for the user, as in this output example:

Output Example: 

Name AppID
---- -----

A.
Datum Pro Center Datum.ProCenter
Proseware Studio Proseware.Studio.5
A.
Datum 2010 prog..tion_0000000000000000_ebec13db489e8ef9
Fabrikam Initializer Fabrikam.Initializer.1
A.
Datum Connector Contoso.Datum.Connector
Proseware Design Pro Proseware.Design.3

## NOTES

## RELATED LINKS

[Export-StartLayout](./Export-StartLayout.md)

[Import-StartLayout](./Import-StartLayout.md)


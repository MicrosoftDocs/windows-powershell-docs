---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.StartLayout.Commands.dll-help.xml
Module Name: StartLayout
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/startlayout/get-startapps?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StartApps
---

# Get-StartApps

## SYNOPSIS
Gets the names and AppIDs of installed apps.

## SYNTAX

```
Get-StartApps [[-Name] <Object>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StartApps** cmdlet gets the names and AppIDs of installed apps of the current user.
An AppID is an AppUserModelID.
You can specify a particular app by using its name, or you can specify a name that includes the wildcard character (*).
If you do not specify a name, the cmdlet displays all installed apps.

## EXAMPLES

### Example 1: Get all apps
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

This command gets all the names and IDs of installed apps for the current user.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

[Start Layout Cmdlets](./startlayout.md)


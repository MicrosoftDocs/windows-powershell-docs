---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/get-appvclientapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppvClientApplication
---

# Get-AppvClientApplication

## SYNOPSIS
Returns applications that are part of App-V Client Packages.

## SYNTAX

```
Get-AppvClientApplication [[-Name] <String>] [[-Version] <String>] [-All] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvClientApplication** cmdlet returns a set of applications that are part of Microsoft Application Virtualization (App-V) Client Packages, based on the criteria provided.

## EXAMPLES

### Example 1: Get a version of an application for the current user
```
PS C:\> Get-AppvClientApplication -Name "AppName" -Version 1
```

This command gets the application on the client that is published to the user and has the name AppName and is version 1.

### Example 2: Get all applications
```
PS C:\> Get-AppvClientApplication -All
```

This command gets all of the applications on the client.

## PARAMETERS

### -All
Indicates that the cmdlet returns all applications that have been added to the computer, not just those that are visible to the current user.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the application.
This value is obtained from the package manifest.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of the application.
If you do not specify this parameter, the cmdlet operates on all available versions of the applications on the target computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppV.AppvClientPowerShell.AppvClientApplication

## NOTES

## RELATED LINKS

[Get-AppvClientConfiguration](./Get-AppvClientConfiguration.md)


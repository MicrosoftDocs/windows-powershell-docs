---
external help file: ps_mmagent_v1.0.cdxml-help.xml
Module Name: MMAgent
online version: 
schema: 2.0.0
title: Debug-MMAppPrelaunch
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 01B55FF9-63D9-4B4A-A249-3EF16E68F12E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Debug-MMAppPrelaunch

## SYNOPSIS
Provides the ability to debug the application prelaunch of a specific application by triggering the prelaunch to occur and to exit debug mode for the application.

## SYNTAX

```
Debug-MMAppPrelaunch -PackageFullName <String> [-DisableDebugMode] -PackageRelativeAppId <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
Prelaunching is a new feature added in Windows® 8.1 that improves the launch performance of apps from the Windows Store by proactively launching frequently used apps in the background if they are not already running or suspended.
This makes starting an app as fast as switching to a suspended app from the user's perspective.
This command enables you to prelaunch an app into debug mode.

You identify the application to prelaunch by including the -PackageFullName and -PackageRelativeAppId parameters.

To turn off debugging, specify the application and also include the -DisableDebugMode.

## EXAMPLES

### Example 1: Prelaunch an app and enable debug mode
```
PS C:\>Debug-MmAppPreLaunch -PackageFullName Microsoft.ZuneMusic_2.0.94.0_x64__8wekyb3d8bbwe -PackageRelativeAppId Microsoft.ZuneMusic
```

This command prelaunches an application in debug mode.

### Example 2: Clear debug mode from the prelaunch activated app
```
PS C:\>Debug-MmAppPreLaunch -PackageFullName Microsoft.ZuneMusic_2.0.94.0_x64__8wekyb3d8bbwe -PackageRelativeAppId Microsoft.ZuneMusic -DisableDebugMode
```

This command disables the debug mode from the app that you previously prelaunch activated.

### Example 3: Getting the PackageFullName and PackageRelativeAppId of your App
```
PS C:\>ForEach ($Package in Get-AppxPackage) {ForEach ($AppRelativeId in (Get-AppxPackageManifest($Package)).Package.Applications.Application.Id) {'PackageFullName: ' + $Package.PackageFullName; 'PackageRelativeId: ' + $AppRelativeID; ''}}
```

This command shows how you can find the PackageFullName and PackageRelativeAppId information for your package.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDebugMode
Specifies that debug mode for the selected application is turned off.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ddm

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PackageFullName
Specifies the AppX package full name containing the application to be prelaunched in debug mode.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pfn

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PackageRelativeAppId
Specifies the application ID of the application within the AppX package to be prelaunched.
The application ID is found in the package manifest file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: praid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

## NOTES
* None

## RELATED LINKS

[Disable-MMAgent](./Disable-MMAgent.md)

[Enable-MMAgent](./Enable-MMAgent.md)

[Get-MMAgent](./Get-MMAgent.md)

[Set-MMAgent](./Set-MMAgent.md)


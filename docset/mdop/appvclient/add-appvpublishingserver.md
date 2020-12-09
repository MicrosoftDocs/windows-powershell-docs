---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: A77E6F2F-2170-41E1-9227-5A9EE1E1C4C0
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-AppvPublishingServer
---

# Add-AppvPublishingServer

## SYNOPSIS
Adds a publishing server for the computer running the App-V client.

## SYNTAX

```
Add-AppvPublishingServer [-Name] <String> [-URL] <String> [[-GlobalRefreshEnabled] <Boolean>]
 [[-GlobalRefreshOnLogon] <Boolean>] [[-GlobalRefreshInterval] <UInt32>]
 [[-GlobalRefreshIntervalUnit] <IntervalUnit>] [[-UserRefreshEnabled] <Boolean>]
 [[-UserRefreshOnLogon] <Boolean>] [[-UserRefreshInterval] <UInt32>]
 [[-UserRefreshIntervalUnit] <IntervalUnit>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AppvPublishingServer** cmdlet adds a new publishing server for the computer running the Microsoft Application Virtualization (App-V) client to connect to.
After the server has been added, the computer running the App-V client is able to use the server to obtain publishing refresh data, stream packages, and perform other operations.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -GlobalRefreshEnabled
Specifies whether to turn on the refreshing of the publishing server for all packages that are published globally.
You can set the refresh to be at the time of logon or on a defined time interval.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalRefreshInterval
Specifies the time interval for the refresh of globally published packages.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalRefreshIntervalUnit
Specifies the unit of time measurement.
Valid values are: day and hour.

```yaml
Type: IntervalUnit
Parameter Sets: (All)
Aliases: 
Accepted values: Hour, Day

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalRefreshOnLogon
Specifies whether a refresh of all packages published to globally occurs every time a user logs into the target computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the publishing server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -URL
Specifies the URL path to the App-V publishing server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRefreshEnabled
Specifies whether to turn on the refreshing of the publishing server for all packages that are published to the user.
The refresh can be set to be at the time of logon or on a defined time interval.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRefreshInterval
Specifies the time interval for refreshes of user-published packages.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRefreshIntervalUnit
Specifies the unit of time measurement.
Valid values are: day and hour.

```yaml
Type: IntervalUnit
Parameter Sets: (All)
Aliases: 
Accepted values: Hour, Day

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRefreshOnLogon
Specifies whether a refresh of all packages published to the user occurs every time a user logs into the target computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppvAgent.AppvPublishingServer

## NOTES

## RELATED LINKS

[Get-AppvPublishingServer](./Get-AppvPublishingServer.md)

[Remove-AppvPublishingServer](./Remove-AppvPublishingServer.md)

[Set-AppvPublishingServer](./Set-AppvPublishingServer.md)

[Sync-AppvPublishingServer](./Sync-AppvPublishingServer.md)



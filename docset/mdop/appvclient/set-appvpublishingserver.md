---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: kenwith
ms.prod: w10
ms.sitesec: library
author: kenwith
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: EF3EA193-6260-4C23-890B-503B79B6EF40
ms.date: 2016-12-05
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-AppvPublishingServer
---

# Set-AppvPublishingServer

## SYNOPSIS
Modifies properties of an App-V Publishing Server.

## SYNTAX

### ByServerId (Default)
```
Set-AppvPublishingServer [-ServerId] <UInt32> [[-GlobalRefreshEnabled] <Boolean>]
 [[-GlobalRefreshOnLogon] <Boolean>] [[-GlobalRefreshInterval] <UInt32>]
 [[-GlobalRefreshIntervalUnit] <IntervalUnit>] [[-UserRefreshEnabled] <Boolean>]
 [[-UserRefreshOnLogon] <Boolean>] [[-UserRefreshInterval] <UInt32>]
 [[-UserRefreshIntervalUnit] <IntervalUnit>] [<CommonParameters>]
```

### ByObject
```
Set-AppvPublishingServer [-Server] <AppvPublishingServer> [[-GlobalRefreshEnabled] <Boolean>]
 [[-GlobalRefreshOnLogon] <Boolean>] [[-GlobalRefreshInterval] <UInt32>]
 [[-GlobalRefreshIntervalUnit] <IntervalUnit>] [[-UserRefreshEnabled] <Boolean>]
 [[-UserRefreshOnLogon] <Boolean>] [[-UserRefreshInterval] <UInt32>]
 [[-UserRefreshIntervalUnit] <IntervalUnit>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppvPublishingServer** cmdlet modifies properties of an already existing Microsoft Application Virtualization (App-V) Publishing Server.
To obtain an App-V Publishing Server object, use the **Get-AppVPublishingServer** cmdlet.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -GlobalRefreshEnabled
Specifies whether the server does automatic syncs with the publishing server for all globally published packages.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalRefreshInterval
Specifies a time span representing the period where refreshes occur for packages published globally.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalRefreshOnLogon
Specifies whether a refresh occurs for all package published globally every time a user logs into the target computer.

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

### -Server
Not Specified.

```yaml
Type: AppvPublishingServer
Parameter Sets: ByObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServerId
Specifies the identifier for the App-V Publishing Server.
This can be queried using the **Get-AppvPublishingServer** cmdlet.

```yaml
Type: UInt32
Parameter Sets: ByServerId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRefreshEnabled
```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRefreshInterval
Specifies a time span representing the period when refreshes occur for packages published to the user.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRefreshIntervalUnit
Specifies the unit of time measurement.
Valid values are:  day and hour.

```yaml
Type: IntervalUnit
Parameter Sets: (All)
Aliases: 
Accepted values: Hour, Day

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRefreshOnLogon
Specifies whether a refresh occurs every time a user logs into the computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AppvAgent.AppvPublishingServer

## OUTPUTS

### Microsoft.AppvAgent.AppvPublishingServer

## NOTES

## RELATED LINKS

[Add-AppvPublishingServer](./Add-AppvPublishingServer.md)

[Get-AppvPublishingServer](./Get-AppvPublishingServer.md)

[Remove-AppvPublishingServer](./Remove-AppvPublishingServer.md)

[Sync-AppvPublishingServer](./Sync-AppvPublishingServer.md)



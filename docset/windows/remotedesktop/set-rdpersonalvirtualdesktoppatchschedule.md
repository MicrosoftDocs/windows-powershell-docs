---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: 
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-RDPersonalVirtualDesktopPatchSchedule
ms.reviewer:
ms.assetid: 0C8EF139-A219-4678-ABF0-7A44CD543B5F
---

# Set-RDPersonalVirtualDesktopPatchSchedule

## SYNOPSIS
Changes patch schedule settings for a personal virtual desktop.

## SYNTAX

```
Set-RDPersonalVirtualDesktopPatchSchedule [-VirtualDesktopName] <String> [-ID] <String> [[-Context] <Byte[]>]
 [[-Deadline] <DateTime>] [[-StartTime] <DateTime>] [[-EndTime] <DateTime>] [[-Label] <String>]
 [[-Plugin] <String>] [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDPersonalVirtualDesktopPatchSchedule** cmdlet changes patch schedule settings for a personal virtual desktop.

## EXAMPLES

### Example 1: Set a default patch schedule for a virtual desktop
```
PS C:\> Set-RDPersonalVirtualDesktopPatchSchedule -VirtualDesktopName "RDS-WKS-A27" -ID "{58E69A71-AFC9-49A6-81B9-494DA20216AC}"
```

This command sets the patch schedule  that has the ID 58E69A71-AFC9-49A6-81B9-494DA20216AC for the personal virtual desktop named RDS-WKS-A27.

### Example 2: Set a patch schedule for a personal virtual desktop
```
PS C:\> Set-RDPersonalVirtualDesktopPatchSchedule -VirtualDesktopName "RDS-WKS-A27" -ID "{58E69A71-AFC9-49A6-81B9-494DA20216AC}" -StartTime (Get-Date)
```

This command sets properties of the path schedule that has the ID 58E69A71-AFC9-49A6-81B9-494DA20216AC for the personal virtual desktop named RDS-WKS-A27.
The **StartTime** parameter specifies the current time as the earliest time by which to begin the patch operation.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
Specifies an array of binary data that the program performing the patch operation uses.
This data is transparent to the user.

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deadline
Specifies a date and time, as a **DateTime** object, by which the patch operation must be complete.
The server uses this value to prioritize the order in which patches are installed.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Specifies the latest date and time, as a **DateTime** object, by which the patch operation must begin.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the ID of a patch schedule.

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

### -Label
Specifies a string that describes the purpose of the patch.
Add a user-friendly, descriptive string so that the patch is easy to distinguish from other, potentially similar patches.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Plugin
Specifies name for the program that installs the patches.
For example, Windows Update.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies the earliest date and time, as a **DateTime** object, by which to begin the patch operation.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of a personal virtual desktop.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDPersonalVirtualDesktopPatchSchedule](./Get-RDPersonalVirtualDesktopPatchSchedule.md)

[New-RDPersonalVirtualDesktopPatchSchedule](./New-RDPersonalVirtualDesktopPatchSchedule.md)

[Remove-RDPersonalVirtualDesktopPatchSchedule](./Remove-RDPersonalVirtualDesktopPatchSchedule.md)


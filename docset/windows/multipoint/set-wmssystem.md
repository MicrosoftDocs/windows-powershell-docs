---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-WmsSystem
ms.reviewer:
ms.assetid: 17BC819F-5550-4290-BCF7-07CBC205C054
---

# Set-WmsSystem

## SYNOPSIS
Modifies system properties.

## SYNTAX

```
Set-WmsSystem [-BootToConsoleMode <Boolean>] [-DesktopMonitoring <Boolean>] [-IM <Boolean>]
 [-IPPerSession <Boolean>] [-Mode <SystemOperatingModePS>] [-SingleSessionPerUser <Boolean>]
 [-SuppressPrivacyNotification <Boolean>] [-AdminOrchestration <Boolean>] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WmsSystem** cmdlet modifies system properties for a MultiPoint Server system.

## EXAMPLES

### Example 1: Modify system settings
```
PS C:\> Set-WmsSystem -CEIP $True -DesktopMonitoring $True
```

This command enables the Customer Experience Improvement Program (CEIP) for the current system and also enables the current system desktop to be monitored.

## PARAMETERS

### -AdminOrchestration
{{Fill AdminOrchestration Description}}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: IsAdminOrchestrationEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BootToConsoleMode
Indicates whether to enable Boot to Console Mode.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DesktopMonitoring
Indicates whether to allow desktop monitoring.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: IsDesktopMonitoringAllowed

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IM
Indicates whether to enable the chat feature.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: IsChatEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPPerSession
Indicates whether to assign each session a unique IP address.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: IsIPPerSessionEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Mode
Specifies the mode.
The acceptable values for this parameter are: Console, MultiStation.

```yaml
Type: SystemOperatingModePS
Parameter Sets: (All)
Aliases: 
Accepted values: Console, MultiStation

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SingleSessionPerUser
Indicates whether a user can log on to multiple stations with the same user account.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: IsSingleSessionPerUser

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SuppressPrivacyNotification
Indicates whether to disable privacy notificationfor standard users.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-WmsSystem](./Add-WmsSystem.md)

[Get-WmsSystem](./Get-WmsSystem.md)

[Remove-WmsSystem](./Remove-WmsSystem.md)

[Restart-WmsSystem](./Restart-WmsSystem.md)

[Search-WmsSystem](./Search-WmsSystem.md)

[Stop-WmsSystem](./Stop-WmsSystem.md)


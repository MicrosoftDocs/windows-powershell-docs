---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-HcsSystem
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 27698C2C-ADD2-48B9-85EE-CD4270F6042A
---

# Get-HcsSystem

## SYNOPSIS
Gets system information about this StorSimple device.

## SYNTAX

```
Get-HcsSystem [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsSystem** cmdlet gets system information about this StorSimple device.
The information returned includes the model type, software version, serial number, and time zone.

## EXAMPLES

### Example 1: Get StorSimple information
```
PS C:\> Get-HcsSystem
InstanceId           : 7ad8891d-f04b-41c6-8634-0eb7e3945c0e
Name                 : 2200-SHX0923218G34GS
Model                : 2200
SerialNumber         : SHX0923218G34GS
TimeZone             : (UTC-08:00) Pacific Time (US &amp; Canada)
CurrentController    : Controller1
ActiveController     : Controller1
Controller0Status    : Normal
Controller1Status    : Normal
SystemMode           : Normal
HcsSoftwareVersion   : 6.3.9600.16517
ApiVersion           : 9.0.0.0
VhdVersion           : 6.3.9600.16517
OSVersion            : 6.3.9600.0
Capacity             : 549755813888000
RemoteManagementMode : HttpsAndHttpEnabled
```

This command gets information about your StorSimple instance.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Platform.Support.SystemInfo
The SystemInfo object has the following properties:

- Guid InstanceId 
- String Name 
- String Model 
- String SerialNumber 
- TimeZoneInfo TimeZone 
- ControllerId CurrentController 
- ControllerId ActiveController 
- ControllerStatus Controller0Status 
- ControllerStatus Controller1Status 
- SystemMode @SystemMode 
- Version HcsSoftwareVersion 
- Version ApiVersion 
- Version VhdVersion 
- Version OSVersion 
- UInt64 Capacity 
- RemoteManagementMode RemoteManagementMode

The ControllerId enumeration has the following values:

- Unknown = controller_id.CONTROLLER_ID_UNKNOWN 
- None = controller_id.CONTROLLER_ID_NONE
- Controller0 = controller_id.CONTROLLER_ID_A
- Controller1 = controller_id.CONTROLLER_ID_B

The ControllerStatus enumeration has the following values:

- Normal 
- Recovery 
- Unreachable

The SystemMode enumeration has the following values:

- Normal 
- Maintenance 
- Decommissioned

The RemoteManagementMode enumeration has the following values:

- HttpsAndHttpEnabled = 0
- HttpsEnabled = 1
- Disabled = 2

## NOTES

## RELATED LINKS

[Set-HcsSystem](./Set-HcsSystem.md)


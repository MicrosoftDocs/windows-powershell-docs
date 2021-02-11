---
external help file: FsrmAdrSetting.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: Get-FsrmAdrSetting
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 6C17626A-58B9-4E6A-AD4B-72E362AEB4F8
---

# Get-FsrmAdrSetting

## SYNOPSIS
Gets access denied remediation settings for events.

## SYNTAX

```
Get-FsrmAdrSetting [[-Event] <FsrmAdrEventEnum[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmAdrSetting** cmdlet gets access denied remediation (ADR) settings in File Server Resource Manager (FSRM) for one or more events.

Windows Server® 2012 uses the ADR settings when a client cannot access a file.
Users get an access-denied message when they try to access shared files and folders on a file server for which they do not have permissions.

## EXAMPLES

### Example 1: Get FSRM access denied settings
```
PS C:\>Get-FsrmAdrSetting -Event AccessDenied
```

This command gets all access denied settings in FSRM.

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

### -Event
Specifies an array of types of events that ADR handles.
The acceptable values for this parameter are: AccessDenied and FileNotFound.

```yaml
Type: FsrmAdrEventEnum[]
Parameter Sets: (All)
Aliases: 
Accepted values: AccessDenied, FileNotFound

Required: False
Position: 1
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMADRSettings

## NOTES

## RELATED LINKS

[Set-FsrmAdrSetting](./Set-FsrmAdrSetting.md)


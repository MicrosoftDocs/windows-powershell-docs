---
external help file: MSFT_NetQosDcbxSetting.cdxml-help.xml
Module Name: DcbQos
online version: 
schema: 2.0.0
title: Get-NetQosDcbxSetting
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 922F1C02-895E-42C1-B1CE-30667A6CEA07
---

# Get-NetQosDcbxSetting

## SYNOPSIS
Gets the data center bridging exchange (DCBX) settings.

## SYNTAX

```
Get-NetQosDcbxSetting [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetQosDcbxSetting** cmdlet allows users to get the data center bridging exchange (DCBX) settings.
The only setting that Windows Server® 2012 allows a user to configure is whether the network adapters in the computer running Windows Server 2012 or later should accept data center bridging (DCB) configurations from the computer or from a remote device.

DCB is the IEEE standard.
DCBX is part of the DCB standard.
Windows Server 2012 and later does not implement DCBX.
Some network adapters may implement DCBX.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetQosDcbxSetting
Willing 
------- 
True
```

This example shows that the computer, such as all DCB capable network adapters, is willing to accept configurations from a remote peer.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosDcbxSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
The MSFT_NetQosDcbxSettingData output object contains the DCBX setting configured in Windows Server 2012 and later.

## NOTES

## RELATED LINKS

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)


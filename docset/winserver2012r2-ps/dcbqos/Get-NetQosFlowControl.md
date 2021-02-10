---
external help file: MSFT_NetQosFlowControl.cdxml-help.xml
Module Name: DcbQos
online version: 
schema: 2.0.0
title: Get-NetQosFlowControl
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C42A7FA6-75A9-4E20-8A8D-8F9F28A35C88
---

# Get-NetQosFlowControl

## SYNOPSIS
Gets the priority-based flow control (PFC) settings.

## SYNTAX

```
Get-NetQosFlowControl [[-Priority] <Byte[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetQosFlowControl** cmdlet gets the priority-based flow control (PFC) settings programmed in Windows Server® 2012 and later.

For more information on PFC, see the Enable-NetQosFlowControl cmdlet.

PFC is part of the IEEE data center bridging (DCB) standard.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetQosFlowControl
Priority   Enabled 
--------   ------- 
0          False 
1          False 
2          False 
3          True 
4          False 
5          False 
6          False 
7          False
```

This example displays flow control settings.

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

### -Priority
Specifies the IEEE 802.1p priority value.

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosFlowControlSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
The MSFT_NetQosFlowControlSettingData object contains the flow control settings per priority.

## NOTES

## RELATED LINKS

[Enable-NetQosFlowControl](./Enable-NetQosFlowControl.md)

[Disable-NetQosFlowControl](./Disable-NetQosFlowControl.md)

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)

[Set-NetQosFlowControl](./Set-NetQosFlowControl.md)


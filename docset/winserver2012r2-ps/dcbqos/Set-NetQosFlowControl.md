---
external help file: MSFT_NetQosFlowControl.cdxml-help.xml
Module Name: DcbQos
online version: 
schema: 2.0.0
title: Set-NetQosFlowControl
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 04AA0089-AD47-46ED-9B16-370F5B785196
---

# Set-NetQosFlowControl

## SYNOPSIS
Sets the flow control settings.

## SYNTAX

### ByPriority (Default)
```
Set-NetQosFlowControl [[-Priority] <Byte[]>] [-Enabled <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetQosFlowControl -InputObject <CimInstance[]> [-Enabled <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetQosFlowControl** cmdlet set the enabled state of priority-based flow control (PFC) in Windows Server® 2012 and later.
If Windows Server 2012 or later is set to be not willing to accept configurations from a remote device, Windows Server 2012 or later will send the updated settings to data center bridging (DCB)-capable network adapters in the computer.

For more information on remote device configurations, see the Set-NetQosDcbxSetting cmdlet.

Priority-based flow control (PFC) is part of the IEEE data center bridging (DCB) standard.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-NetQosFlowControl -Priority 5 -Enabled $true
```

This example enables flow control on traffic tagged with priority 5.
This cmdlet is equivalent to the Enable-NetQosFlowControl with priority 5.

### EXAMPLE 2
```
PS C:\> Get-NetQosFlowControl -Priority 5 | Set-NetQosFlowControl -Enabled $false
```

This example gets the flow control settings for traffic tagged with priority 5 and disables the flow control settings.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Sets the enabled state for flow control based on priority values.

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

### -InputObject
Specified the object which will be modified by this cmdlet.
The object must be piped to the cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Priority
Specifies the IEEE 802.1p priority value.

```yaml
Type: Byte[]
Parameter Sets: ByPriority
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosFlowControlSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
The MSFT_NetQosFlowControlSettingData object contains the flow control setting per priority.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosFlowControlSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
The MSFT_NetQosFlowControlSettingData object contains flow control settings per priority.
Only when the **PassThru** parameter is specified will this cmdlet return the MSFT_NetQosFlowControlSettingData object.

## NOTES

## RELATED LINKS

[Disable-NetQosFlowControl](./Disable-NetQosFlowControl.md)

[Enable-NetQosFlowControl](./Enable-NetQosFlowControl.md)

[Get-NetQosFlowControl](./Get-NetQosFlowControl.md)

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)


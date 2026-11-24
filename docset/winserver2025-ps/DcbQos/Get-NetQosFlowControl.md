---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetQosFlowControl.cdxml-help.xml
Module Name: DcbQos
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/dcbqos/get-netqosflowcontrol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetQosFlowControl
---

# Get-NetQosFlowControl

## SYNOPSIS
Gets the priority-based flow control settings.

## SYNTAX

### ByIfAlias (Default)
```
Get-NetQosFlowControl [[-Priority] <Byte[]>] [[-InterfaceAlias] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIfIndex
```
Get-NetQosFlowControl [[-Priority] <Byte[]>] [[-InterfaceIndex] <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetQosFlowControl** cmdlet gets the priority-based flow control (PFC) settings programmed in Windows Server® 2012 and later.

For more information about PFC, see the **Enable-NetQosFlowControl** cmdlet.

PFC is part of the IEEE data center bridging (DCB) standard.

## EXAMPLES

### Example 1: Display flow control settings
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

This command displays flow control settings.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -InterfaceAlias
```yaml
Type: String
Parameter Sets: ByIfAlias
Aliases: IfAlias

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
```yaml
Type: UInt32
Parameter Sets: ByIfIndex
Aliases: IfIndex

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Priority
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.UInt32

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosFlowControlSettingData

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
This cmdlet returns a **MSFT_NetQosFlowControlSettingData** object that contains the flow control settings per priority.

## NOTES

## RELATED LINKS

[Enable-NetQosFlowControl](./Enable-NetQosFlowControl.md)

[Disable-NetQosFlowControl](./Disable-NetQosFlowControl.md)

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)

[Set-NetQosFlowControl](./Set-NetQosFlowControl.md)


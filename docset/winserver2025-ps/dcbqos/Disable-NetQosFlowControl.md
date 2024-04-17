---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetQosFlowControl.cdxml-help.xml
Module Name: DcbQos
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/dcbqos/disable-netqosflowcontrol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-NetQosFlowControl
---

# Disable-NetQosFlowControl

## SYNOPSIS
Disables link level flow control based on the IEEE 802.1p priority.

## SYNTAX

### ByIfAlias (Default)
```
Disable-NetQosFlowControl [[-Priority] <Byte[]>] [[-InterfaceAlias] <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByIfIndex
```
Disable-NetQosFlowControl [[-Priority] <Byte[]>] [[-InterfaceIndex] <UInt32>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Disable-NetQosFlowControl -InputObject <CimInstance[]> [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-NetQosFlowControl** cmdlet disables priority-based flow control (PFC) in Windows Server® 2012 and later.
PFC is part of the IEEE data center bridging (DCB) standard.
If Windows Server 2012 or later is configured to be **not willing** to accept configurations from a remote device, Windows Server 2012 or later programs DCB capable network adapters, which disables PFC at the link level.

For more information about remote device configurations, see the **Set-NetQosDcbxSetting** cmdlet.

For more information about PFC, see the **Enable-NetQosFlowControl** cmdlet.

## EXAMPLES

### Example 1: Disable flow control on traffic for a priority
```
PS C:\> Disable-NetQosFlowControl -Priority 6
```

This command disables flow control on traffic tagged with priority 6.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -PassThru
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
```yaml
Type: Byte[]
Parameter Sets: ByIfAlias, ByIfIndex
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.UInt32

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Enable-NetQosFlowControl](./Enable-NetQosFlowControl.md)

[Get-NetQosFlowControl](./Get-NetQosFlowControl.md)

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)

[Set-NetQosFlowControl](./Set-NetQosFlowControl.md)


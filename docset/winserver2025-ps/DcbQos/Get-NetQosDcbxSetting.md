---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetQosDcbxSetting.cdxml-help.xml
Module Name: DcbQos
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/dcbqos/get-netqosdcbxsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetQosDcbxSetting
---

# Get-NetQosDcbxSetting

## SYNOPSIS
Gets data center bridging exchange settings.

## SYNTAX

### ByIfAlias (Default)
```
Get-NetQosDcbxSetting [[-InterfaceAlias] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByIfIndex
```
Get-NetQosDcbxSetting [[-InterfaceIndex] <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetQosDcbxSetting** cmdlet gets data center bridging exchange (DCBX) settings.
The only setting that Windows Server® 2012 allows you to configure is whether the network adapters in the computer that runs Windows Server 2012 or later  accepts data center bridging (DCB) configurations from the computer or from a remote device.

DCB is the IEEE standard.
DCBX is part of the DCB standard.
Windows Server 2012 and later does not implement DCBX.
Some network adapters may implement DCBX.

## EXAMPLES

### Example 1: Display settings for a computer
```
PS C:\> Get-NetQosDcbxSetting
Willing
-------
True
```

This command shows that the computer is willing to accept configurations from a remote peer.

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
Position: 0
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosDcbxSettingData

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
This cmdlet returns a **MSFT_NetQosDcbxSettingData** object that contains the DCBX setting configured in Windows Server 2012 and later.

## NOTES

## RELATED LINKS

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)


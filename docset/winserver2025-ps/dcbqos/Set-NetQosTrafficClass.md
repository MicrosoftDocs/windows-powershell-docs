---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetQosTrafficClass.cdxml-help.xml
Module Name: DcbQos
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/dcbqos/set-netqostrafficclass?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetQosTrafficClass
---

# Set-NetQosTrafficClass

## SYNOPSIS
Sets the traffic class settings.

## SYNTAX

### ByIfAlias (Default)
```
Set-NetQosTrafficClass [[-Name] <String[]>] [[-InterfaceAlias] <String>] [-Algorithm <Algorithm>]
 [-BandwidthPercentage <Byte>] [-Priority <Byte[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByIfIndex
```
Set-NetQosTrafficClass [[-Name] <String[]>] [[-InterfaceIndex] <UInt32>] [-Algorithm <Algorithm>]
 [-BandwidthPercentage <Byte>] [-Priority <Byte[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetQosTrafficClass -InputObject <CimInstance[]> [-Algorithm <Algorithm>] [-BandwidthPercentage <Byte>]
 [-Priority <Byte[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetQosTrafficClass** cmdlet modifies the settings of a traffic class, such as the mapping between 802.1p priority and traffic class, the transmission algorithm that must be used, and the bandwidth allocation to the traffic class.
If Windows Server® 2012 or later is set to be **not willing** to accept configurations from a remote device, then Windows Server 2012 or later sends the updated settings to data center bridging (DCB)-capable network adapters in the computer.

For more information about remote device configurations, see the **Set-NetQosDcbxSetting** cmdlet.

For more information about traffic class, see the **New-NetQosTrafficClass** cmdlet.

## EXAMPLES

### Example 1: Change the bandwidth allocation for a traffic class
```
PS C:\> Set-NetQosTrafficClass -Name "SMB" -BandwidthPercentage 50
```

This command changes the bandwidth allocation to traffic class named SMB to 50 percent.

### Example 2: Change the priority mapping for a traffic class
```
PS C:\> Get-NetQosTrafficClass -Name "SMB" | Set-NetQosTrafficClass -Priority 3,4
```

This command gets the settings of the traffic class named SMB by using the **Get-NetQosTrafficClass** cmdlet.
The command passes them to the current cmdlet by using the pipeline operator.
That cmdlet changes the priority mapping setting so that traffic tagged with 3 or 4 are mapped to the traffic class named SMB.

## PARAMETERS

### -Algorithm
```yaml
Type: Algorithm
Parameter Sets: (All)
Aliases: tsa
Accepted values: Strict, ETS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -BandwidthPercentage
```yaml
Type: Byte
Parameter Sets: (All)
Aliases: Bandwidth, bw

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Name
```yaml
Type: String[]
Parameter Sets: ByIfAlias, ByIfIndex
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
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
Parameter Sets: (All)
Aliases: p, pri

Required: False
Position: Named
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

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.NetQosTrafficClass.Algorithm

### System.Byte

### System.Byte[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosTrafficClassSettingData

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
This cmdlet returns a **MSFT_NetQosTrafficClassSettingData** object contains a network traffic class.
Only if you specify the *PassThru* parameter does the cmdlet return the **MSFT_NetQosTrafficClassSettingData** object.

## NOTES

## RELATED LINKS

[Get-NetQosTrafficClass](./Get-NetQosTrafficClass.md)

[New-NetQosTrafficClass](./New-NetQosTrafficClass.md)

[Remove-NetQosTrafficClass](./Remove-NetQosTrafficClass.md)

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)

[Set-NetQosTrafficClass](./Set-NetQosTrafficClass.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterChecksumOffload.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/set-netadapterchecksumoffload?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetAdapterChecksumOffload
---

# Set-NetAdapterChecksumOffload

## SYNOPSIS
Sets the various checksum offload settings.

## SYNTAX

### ByName (Default)
```
Set-NetAdapterChecksumOffload [-Name] <String[]> [-IncludeHidden] [-IpIPv4Enabled <Direction>]
 [-TcpIPv4Enabled <Direction>] [-TcpIPv6Enabled <Direction>] [-UdpIPv4Enabled <Direction>]
 [-UdpIPv6Enabled <Direction>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapterChecksumOffload -InterfaceDescription <String[]> [-IncludeHidden] [-IpIPv4Enabled <Direction>]
 [-TcpIPv4Enabled <Direction>] [-TcpIPv6Enabled <Direction>] [-UdpIPv4Enabled <Direction>]
 [-UdpIPv6Enabled <Direction>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapterChecksumOffload -InputObject <CimInstance[]> [-IpIPv4Enabled <Direction>]
 [-TcpIPv4Enabled <Direction>] [-TcpIPv6Enabled <Direction>] [-UdpIPv4Enabled <Direction>]
 [-UdpIPv6Enabled <Direction>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapterChecksumOffload** cmdlet sets the state of the checksum offload properties.
The network adapter computes the checksums, therefore reducing processor utilization because the processor is not performing this computation.
This cmdlet sets the various checksum offload settings, including IPv4, TCPv4, TCPv6, UDPv4, and UDPv6.
This cmdlet enables a few types of checksums while disabling others.
If only setting the enabled state, run the **Enable-NetAdapterChecksumOffload** or **Disable-NetAdapterChecksumOffload** cmdlet.

## EXAMPLES

### Example 1: Enable IPv4 checksum for both receive and transmit directions on all network adapters
```
PS C:\> Set-NetAdapterChecksumOffload -Name "*" -IpIPv4Enabled RxTxEnabled
```

This command enables the IPv4 checksum offload for both receive and transmit directions on all visible network adapters.

### Example 2: Enable IPv4, UDPv4, and TCPv4 checksums for both receive and transmit directions on all network adapters
```
PS C:\> Set-NetAdapterChecksumOffload -Name "MyAdapter" -IpIPv4Enabled RxTxEnabled -TcpIpv4Enabled RxTxEnabled -UdpIpv4Enabled RxTxEnabled
```

This command enables the IPv4 checksum, the UDPv4 checksum, and the TCPv4 checksum in both receive and transmit directions on the network adapter named MyAdapter.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -IncludeHidden
Indicates that the cmdlet includes both visible and hidden network adapters in the operation.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: ByName, ByInstanceID
Aliases:

Required: False
Position: Named
Default value: None
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

### -InterfaceDescription
Specifies an array of network adapter interface descriptions.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc, InstanceID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpIPv4Enabled
Specifies the direction of the IP traffic for IPv4.
The acceptable values for this parameter are:

- Disabled
- RxTxEnabled
- RxEnabled
- TxEnabled.

If RxEnabled or TxEnabled is selected, then the opposite direction (transmit or receive, respectively) is disabled.
Such as if the state is RxEnabled, then checksum calculations for receive traffic is enabled and for transmit traffic is Disabled.

```yaml
Type: Direction
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, TxEnabled, RxEnabled, RxTxEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of network adapter names.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRestart
Indicates that the cmdlet does not restart the network adapter after completing the operation.
Many advanced properties require restarting the network adapter before the new settings take effect.

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

### -TcpIPv4Enabled
Specifies the direction of the TCP traffic for IPv4.
The acceptable values for this parameter are:

- Disabled
- RxTxEnabled
- RxEnabled
- TxEnabled

If RxEnabled or TxEnabled is selected, then the opposite direction (transmit or receive, respectively) is disabled.
Such as if the state is RxEnabled, then checksum calculations for receive traffic is enabled and for transmit traffic is Disabled.

```yaml
Type: Direction
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, TxEnabled, RxEnabled, RxTxEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TcpIPv6Enabled
Specifies the direction of the TCP traffic for IPv6.
The acceptable values for this parameter are:

- Disabled
- RxTxEnabled
- RxEnabled
- TxEnabled

If RxEnabled or TxEnabled is selected, then the opposite direction (transmit or receive, respectively) is disabled.
Such as if the state is RxEnabled, then checksum calculations for receive traffic is enabled and for transmit traffic is Disabled.

```yaml
Type: Direction
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, TxEnabled, RxEnabled, RxTxEnabled

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

### -UdpIPv4Enabled
Specifies the direction of the UDP traffic for IPv4.
The acceptable values for this parameter are:

- Disabled
- RxTxEnabled
- RxEnabled
- TxEnabled

If RxEnabled or TxEnabled is selected, then the opposite direction (transmit or receive, respectively) is disabled.
Such as if the state is RxEnabled, then checksum calculations for receive traffic is enabled and for transmit traffic is Disabled.

```yaml
Type: Direction
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, TxEnabled, RxEnabled, RxTxEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UdpIPv6Enabled
Specifies the direction of the UDP traffic for IPv6.
The acceptable values for this parameter are:

- Disabled
- RxTxEnabled
- RxEnabled
- TxEnabled.

If RxEnabled or TxEnabled is selected, then the opposite direction (transmit or receive, respectively) is disabled.
Such as if the state is RxEnabled, then checksum calculations for receive traffic is enabled and for transmit traffic is Disabled.

```yaml
Type: Direction
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, TxEnabled, RxEnabled, RxTxEnabled

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter ChecksumOffloadSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter ChecksumOffloadSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterChecksumOffload](./Disable-NetAdapterChecksumOffload.md)

[Enable-NetAdapterChecksumOffload](./Enable-NetAdapterChecksumOffload.md)

[Get-NetAdapterChecksumOffload](./Get-NetAdapterChecksumOffload.md)


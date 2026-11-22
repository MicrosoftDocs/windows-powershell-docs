---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetNat.cdxml-help.xml
Module Name: NetNat
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netnat/set-netnat?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetNat
---

# Set-NetNat

## SYNOPSIS
Modifies settings for NAT objects.

## SYNTAX

### Query (cdxml) (Default)
```
Set-NetNat [-Name] <String[]> [-IcmpQueryTimeout <UInt32>] [-TcpEstablishedConnectionTimeout <UInt32>]
 [-TcpTransientConnectionTimeout <UInt32>] [-TcpFilteringBehavior <FilteringBehaviorType>]
 [-UdpFilteringBehavior <FilteringBehaviorType>] [-UdpIdleSessionTimeout <UInt32>]
 [-UdpInboundRefresh <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetNat -InputObject <CimInstance[]> [-IcmpQueryTimeout <UInt32>]
 [-TcpEstablishedConnectionTimeout <UInt32>] [-TcpTransientConnectionTimeout <UInt32>]
 [-TcpFilteringBehavior <FilteringBehaviorType>] [-UdpFilteringBehavior <FilteringBehaviorType>]
 [-UdpIdleSessionTimeout <UInt32>] [-UdpInboundRefresh <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetNat** cmdlet modifies settings for Network Address Translation (NAT) objects.
NAT modifies IP address and port information in packet headers.
Use this cmdlet to modify the following:

- Time-out values for ICMP and UDP sessions and TCP connections.
- Behavior of TCP and UDP filtering.
- Whether packets from external networks refresh UDP sessions.

Specify NAT objects to modify by using the *Name* parameter or by using the **Get-NetNat** cmdlet.
Use the **New-NetNat** cmdlet to create NAT objects.

## EXAMPLES

### Example 1: Modify settings for a NAT object
```
PS C:\> Set-NetNat -Name "TSQATenant" -TcpFilteringBehavior AddressDependentFiltering -UdpInboundRefresh $True
```

This command modifies a NAT object named TSQATenant.
The command specifies a value of $True for the *UdpInboundRefresh* parameter, and, therefore, NAT refreshes UDP sessions for both inbound and outbound packets.
The command changes TCP filtering behavior to address dependent filtering.

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

### -IcmpQueryTimeout
Specifies the length of the time-out period, in seconds, for an ICMP query session.

```yaml
Type: UInt32
Parameter Sets: (All)
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

### -Name
Specifies an array of names of NAT objects.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -TcpEstablishedConnectionTimeout
Specifies the length of the time-out period, in seconds, for established TCP connections.
Use the *TcpTransientConnectionTimeout* parameter to modify the time-out period for transient TCP connections.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TcpFilteringBehavior
Specifies filtering behavior for TCP connections.
The acceptable values for this parameter are:

- EndpointIndependentFiltering
- AddressDependentFiltering

The default value is EndpointIndependentFiltering.

```yaml
Type: FilteringBehaviorType
Parameter Sets: (All)
Aliases:
Accepted values: EndpointIndependentFiltering, AddressDependentFiltering

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TcpTransientConnectionTimeout
Specifies the length of the time-out period, in seconds, for transient TCP connections.
Use the *TcpEstablishedConnectionTimeout* parameter to modify the time-out period for established TCP connections.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

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

### -UdpFilteringBehavior
Specifies filtering behavior for UDP sessions.
The acceptable values for this parameter are:

- EndpointIndependentFiltering
- AddressDependentFiltering

The default value is EndpointIndependentFiltering.

```yaml
Type: FilteringBehaviorType
Parameter Sets: (All)
Aliases:
Accepted values: EndpointIndependentFiltering, AddressDependentFiltering

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UdpIdleSessionTimeout
Specifies the length of the time-out period, in seconds, for a UDP session.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UdpInboundRefresh
Indicates whether a packet from the external network refreshes an existing UDP session.
If you specify a value of $True for this parameter, either an inbound packet or an outbound packet refreshes an existing UDP session.
If you specify a value of $False, only an outbound packet refreshes a UDP session.
The default value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Accepted values: False, True

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetNat

## NOTES

## RELATED LINKS

[Get-NetNat](./Get-NetNat.md)

[New-NetNat](./New-NetNat.md)

[Remove-NetNat](./Remove-NetNat.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterRsc.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapterrsc?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetAdapterRsc
---

# Get-NetAdapterRsc

## SYNOPSIS
Gets network adapters that support RSC.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterRsc [[-Name] <String[]>] [-IPv4OperationalState <Boolean[]>] [-IPv6OperationalState <Boolean[]>]
 [-IPv4FailureReason <FailureReason[]>] [-IPv6FailureReason <FailureReason[]>] [-IncludeHidden]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterRsc -InterfaceDescription <String[]> [-IPv4OperationalState <Boolean[]>]
 [-IPv6OperationalState <Boolean[]>] [-IPv4FailureReason <FailureReason[]>]
 [-IPv6FailureReason <FailureReason[]>] [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterRsc** cmdlet gets network adapters that support receive segment coalescing (RSC).
RSC takes multiple packets received within the same interrupt period and combines the packets into a single large package to be processed by the network stack.
This reduces the processing overhead for incoming packets and reduces the number of processor cycles that are used, leading to better scalability.

## EXAMPLES

### Example 1: Get the RSC properties for the specified network adapter
```
PS C:\> Get-NetAdapterRsc -Name "MyAdapter"
```

This command gets the RSC properties of the network adapter named MyAdapter.

### Example 2: Get all RSC capable network adapters
```
PS C:\> Get-NetAdapterRsc -Name "*"
```

This command gets all of the RSC capable network adapters.

### Example 3: Get all RSC capable network adapters that have RSC enabled
```
PS C:\> Get-NetAdapterRsc -Name "*" | Where-Object -FilterScript { $_.Enabled }
```

This command gets all of the RSC capable network adapters that have RSC enabled.

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

### -IPv4FailureReason
Specifies the reason that RSC may not be working on IPv4 traffic.

The acceptable values for this parameter are:

- NoFailure
- NicPropertyDisabled
- WFPCompatibility
- NDISCompatibility
- ForwardingEnabled
- NetOffloadGlobalDisabled

```yaml
Type: FailureReason[]
Parameter Sets: (All)
Aliases: 
Accepted values: NoFailure, NicPropertyDisabled, WFPCompatibility, NDISCompatibility, ForwardingEnabled, NetOffloadGlobalDisabled, Capability, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4OperationalState
Specifies the state of the TCP/IP protocol driver for RSC.
See the *IPv4FailureReason* parameter value for more information.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6FailureReason
Returns the reason that of RSC may not be working on IPv6 traffic.

The acceptable values for this parameter are:

- NoFailure
- NicPropertyDisabled
- WFPCompatibility
- NDISCompatibility
- ForwardingEnabled
- NetOffloadGlobalDisabled

If RSC is desired, then the following actions can be taken: 

- NicPropertyDisabled: Run the **Enable-NetAdapterRsc** cmdlet to enable RSC on the specified network adapter. 
- WFPCompatibility: Disable the WFP filters. 
- NDISCompatibility: Upgrade to an NDIS 6.30 driver. 
- ForwardingEnabled: Disable forwarding. 
- NetOffloadGlobalDisabled: Run the **Set-NetOffloadGlobalSetting** cmdlet with the *ReceiveSegmentCoalescing* parameter set to Enabled.

```yaml
Type: FailureReason[]
Parameter Sets: (All)
Aliases: 
Accepted values: NoFailure, NicPropertyDisabled, WFPCompatibility, NDISCompatibility, ForwardingEnabled, NetOffloadGlobalDisabled, Capability, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6OperationalState
Specifies the state of the TCP/IP protocol driver for RSC.
See the *IPv6FailureReason* parameter value for more information.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeHidden
Indicates that the cmdlet includes both visible and hidden network adapters in the operation.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

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

### -Name
Specifies an array of network adapter names.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterRscSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterRsc](./Disable-NetAdapterRsc.md)

[Enable-NetAdapterRsc](./Enable-NetAdapterRsc.md)

[Set-NetAdapterRsc](./Set-NetAdapterRsc.md)


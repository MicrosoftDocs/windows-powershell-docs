---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterRss.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/set-netadapterrss?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetAdapterRss
---

# Set-NetAdapterRss

## SYNOPSIS
Sets the RSS properties on a network adapter.

## SYNTAX

### ByName (Default)
```
Set-NetAdapterRss [-Name] <String[]> [-IncludeHidden] [-NumberOfReceiveQueues <UInt32>] [-Profile <Profile>]
 [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>] [-MaxProcessorGroup <UInt16>]
 [-MaxProcessorNumber <Byte>] [-MaxProcessors <UInt32>] [-NumaNode <UInt16>] [-Enabled <Boolean>] [-NoRestart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapterRss -InterfaceDescription <String[]> [-IncludeHidden] [-NumberOfReceiveQueues <UInt32>]
 [-Profile <Profile>] [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>]
 [-MaxProcessorGroup <UInt16>] [-MaxProcessorNumber <Byte>] [-MaxProcessors <UInt32>] [-NumaNode <UInt16>]
 [-Enabled <Boolean>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapterRss -InputObject <CimInstance[]> [-NumberOfReceiveQueues <UInt32>] [-Profile <Profile>]
 [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>] [-MaxProcessorGroup <UInt16>]
 [-MaxProcessorNumber <Byte>] [-MaxProcessors <UInt32>] [-NumaNode <UInt16>] [-Enabled <Boolean>] [-NoRestart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapterRss** cmdlet sets the receive side scaling (RSS) properties on a network adapter.
RSS is a scalability technology that distributes the receive network traffic among multiple processors by hashing the header of the incoming packet.
If RSS is disabled, network traffic is processed on a single processor core. This may impact network performance as the processor utilization increases.
Many properties can be configured using the parameters to optimize the performance of RSS.
The selection of the processors to use for RSS is an important aspect of load balancing.
Most of the parameters for this cmdlet help to determine the processors used by RSS.
A thorough understanding of RSS is recommended before modifying individual parameters.
Selecting the correct profile should be sufficient in most scenarios.

## EXAMPLES

### Example 1: Set an RSS profile for a NUMA server without dynamic load balancing
```
PS C:\> Set-NetAdapterRss -Name "Ethernet" -Profile NUMAStatic
```

This command sets an RSS profile for a NUMA server without dynamic load balancing on the network adapter named Ethernet.

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

### -BaseProcessorGroup
Specifies the base processor group of a non-uniform memory access (NUMA) node.
This impacts the processor array used by RSS.
This parameter is the lowest group number of any processors that appear in the processor array.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: BaseG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BaseProcessorNumber
Specifies the base processor number of a NUMA node.
This parameter is the lowest processor number of any processors from the *BaseProcessorGroup* parameter that appear in the processor array.
This allows for partitioning processors across network adapters.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: BaseN

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

### -Enabled
Indicates whether RSS on an interface is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### -MaxProcessorGroup
Specifies the maximum processor group of a NUMA node.
This parameter is the highest group number of any processors that appear in the processor array for this network adapter.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: MaxG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxProcessorNumber
Specifies the maximum processor number of a NUMA node.
This parameter is the highest processor number of any processors from the *MaxProcessorGroup* parameter that appear in the processor array for this network adapter.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: MaxN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxProcessors
Specifies the maximum number of processors to be used concurrently by RSS from the processor array for load balancing network transmissions from a single network adapter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Max

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

### -NumaNode
Specifies the NUMA node affinity for a network adapter.
This ensures that a given network transmission is load balanced by RSS within the NUMA node.
This affects the memory allocation and also impacts the preference and ordering of the processors in the processor array.
It does not affect the set of processors contained in the array, but it may impact the subset of the array that RSS actually uses.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfReceiveQueues
Specifies the number of receive queues per network adapter that is to be used by the interface

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

### -Profile
Specifies the RSS profile.

The acceptable values for this parameter are:

- Closest: Behavior is consistent with the behavior of Windows Server® 2008 R2.
- ClosestStatic: No dynamic load balancing, such as distributing but not load balancing at runtime.
- NUMA: Assigns RSS processors in a round robin basis across every NUMA node to enable applications that are running on NUMA servers to scale well.
- NUMAStatic: Default behavior.
RSS processor selection is the same as for NUMA scalability without dynamic load balancing.
- Conservative: RSS uses as few processors as possible to sustain the load.
This option helps reduce the number of interrupts.

```yaml
Type: Profile
Parameter Sets: (All)
Aliases:
Accepted values: Closest, ClosestStatic, NUMA, NUMAStatic, Conservative

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterRssSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterRssSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterRss](./Disable-NetAdapterRss.md)

[Enable-NetAdapterRss](./Enable-NetAdapterRss.md)

[Get-NetAdapterRss](./Get-NetAdapterRss.md)


---
external help file: NetAdapter_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 178058E6-A1EC-4285-8D04-5C6569D7F323
manager: dansimp
---

# Set-NetAdapterRss

## SYNOPSIS
Sets the receive side scaling (RSS) properties on the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetAdapterRss [-Name] <String[]> [-AsJob] [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>]
 [-CimSession <CimSession[]>] [-Enabled <Boolean>] [-IncludeHidden] [-MaxProcessorGroup <UInt16>]
 [-MaxProcessorNumber <Byte>] [-MaxProcessors <UInt32>] [-NoRestart] [-NumaNode <UInt16>]
 [-NumberOfReceiveQueues <UInt32>] [-PassThru] [-Profile <Profile>] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetAdapterRss [-AsJob] [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>]
 [-CimSession <CimSession[]>] [-Enabled <Boolean>] [-IncludeHidden] [-MaxProcessorGroup <UInt16>]
 [-MaxProcessorNumber <Byte>] [-MaxProcessors <UInt32>] [-NoRestart] [-NumaNode <UInt16>]
 [-NumberOfReceiveQueues <UInt32>] [-PassThru] [-Profile <Profile>] [-ThrottleLimit <Int32>]
 -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-NetAdapterRss [-AsJob] [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>]
 [-CimSession <CimSession[]>] [-Enabled <Boolean>] [-MaxProcessorGroup <UInt16>] [-MaxProcessorNumber <Byte>]
 [-MaxProcessors <UInt32>] [-NoRestart] [-NumaNode <UInt16>] [-NumberOfReceiveQueues <UInt32>] [-PassThru]
 [-Profile <Profile>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetAdapterRss** cmdlet sets the receive side scaling (RSS) properties on the network adapter.
RSS is a scalability technology that distributes the receive network traffic among multiple processors by hashing the header of the incoming packet.
Without RSS in firstref_longhorn, firstref_server_7, and Windows Server® 2012; network traffic is received on the first processor which can quickly reach full utilization limiting receive network throughput.
Many properties can be configured using the parameters to optimize the performance of RSS.
The selection of the processors to use for RSS is an important aspect of load balancing.
Most of the parameters for this cmdlet help to determine the processors used by RSS.
A thorough understanding of RSS is recommended before modifying individual parameters.
Selecting the correct profile should be sufficient in most scenarios.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetAdapterRss -Name "Ethernet" -Profile NUMAStatic
```

This example sets an RSS profile for a non-uniform memory access (NUMA) server without dynamic load balancing.

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

### -BaseProcessorGroup
Sets the base processor group of a non-uniform memory access (NUMA) node.
This will impact the processor array used by RSS.
This parameter is the lowest group number of any processors that appear in the processor array.

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

### -BaseProcessorNumber
Sets the base processor number of a NUMA node.
This parameter is the lowest processor number of any processors from the **BaseProcessorGroup** parameter that appear in the processor array.
This allows for partitioning processors across network adapters.

```yaml
Type: Byte
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Sets the enabled state of RSS on an interface

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
Specifies both visible and hidden network adapters should be included.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -MaxProcessorGroup
Sets the maximum processor group of a NUMA node.
This parameter is the highest group number of any processors that appear in the processor array for this network adapter.

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

### -MaxProcessorNumber
Sets the maximum processor number of a NUMA node.
This parameter is the highest processor number of any processors from the **MaxProcessorGroup** parameter that appear in the processor array for this network adapter.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxProcessors
Sets the maximum number of processors to be used concurrently by RSS from the processor array for load balancing network transmissions from a single network adapter.

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

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoRestart
Specifies that the network adapter is not restarted as part of running this cmdlet.
Note: Many advanced properties require restarting the network adapter before the new settings take effect.

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
Sets the NUMA node affinity for a network adapter.
This will ensure that a given network transmission is load balanced by RSS within the NUMA node.
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
The acceptable values for this parameter are: Closest, ClosestStatic, NUMA, NUMAStatic, or Conservative. 

 - Closest: Behavior is consistent with the behavior of firstref_server_7. 

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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


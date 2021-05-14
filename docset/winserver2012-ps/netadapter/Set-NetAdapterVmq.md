---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://docs.microsoft.com/powershell/module/netadapter/set-netadaptervmq?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetAdapterVmq

## SYNOPSIS
Sets the virtual machine queue (VMQ) properties of the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetAdapterVmq [-Name] <String[]> [-AsJob] [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>]
 [-CimSession <CimSession[]>] [-Enabled <Boolean>] [-IncludeHidden] [-MaxProcessorNumber <Byte>]
 [-MaxProcessors <UInt32>] [-NoRestart] [-NumaNode <UInt16>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetAdapterVmq [-AsJob] [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>]
 [-CimSession <CimSession[]>] [-Enabled <Boolean>] [-MaxProcessorNumber <Byte>] [-MaxProcessors <UInt32>]
 [-NoRestart] [-NumaNode <UInt16>] [-PassThru] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-NetAdapterVmq [-AsJob] [-BaseProcessorGroup <UInt16>] [-BaseProcessorNumber <Byte>]
 [-CimSession <CimSession[]>] [-Enabled <Boolean>] [-IncludeHidden] [-MaxProcessorNumber <Byte>]
 [-MaxProcessors <UInt32>] [-NoRestart] [-NumaNode <UInt16>] [-PassThru] [-ThrottleLimit <Int32>]
 -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetAdapterVmq** cmdlet sets the virtual machine queue (VMQ) properties of the network adapter.
VMQ is a scaling networking technology for Hyper-V switch that improves network throughput by distributing processing of network traffic for multiple virtual machines (VMs) among multiple processors.
A thorough familiarity with VMQ and dynamic VMQ is highly recommended before changing any default values with this cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetAdapterVmq -Name MyAdapter -Enabled $True
```

This example enables VMQ on the network adapter named MyAdapter.
Note: The Enable-NetAdapterVmq cmdlet is the preferred cmdlet to perform this operation.

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
Specifies the processor group to be used by VMQ.
Support for systems that have more than `64` logical processors is based on the concept of a processor group, which is a static set of up to `64` logical processors.
Processor groups are numbered starting with `0`.
Computers with fewer than `64` logical processors always have a single group, Group `0`.

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
Specifies the starting processor to be used within the processor group for VMQ.
Support for systems that have more than `64` logical processors is based on the concept of a processor group, which is a static set of up to `64` logical processors.
Processor groups are numbered starting with `0`.
Computers with fewer than `64` logical processors always have a single group, Group `0`.
A logical processor is identified by a group number, using the **BaseProcessorGroup** parameter, and a group-relative processor number, using this parameter.

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
Sets the enabled state of VMQ.
The acceptable values for this parameter are: `$true` or `$false`.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -MaxProcessorNumber
Specifies the largest processor number in the group.

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
Specifies the maximum number of processors used by VMQ for load balancing network transmissions.

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
Specifies the preferred non-uniform memory access (NUMA) node for the affinity of the VMQs allocated on this network adapter.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterVmqSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterVmqSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterVmq](./Disable-NetAdapterVmq.md)

[Enable-NetAdapterVmq](./Enable-NetAdapterVmq.md)

[Get-NetAdapterVmq](./Get-NetAdapterVmq.md)

[Get-NetAdapterVmqQueue](./Get-NetAdapterVmqQueue.md)


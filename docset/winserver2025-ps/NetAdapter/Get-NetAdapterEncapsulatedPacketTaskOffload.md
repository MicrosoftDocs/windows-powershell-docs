---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterEncapsulatedPacketTaskOffload.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapterencapsulatedpackettaskoffload?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetAdapterEncapsulatedPacketTaskOffload
---

# Get-NetAdapterEncapsulatedPacketTaskOffload

## SYNOPSIS
Gets the network adapters that support encapsulated task offload.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterEncapsulatedPacketTaskOffload [[-Name] <String[]>] [-IncludeHidden] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterEncapsulatedPacketTaskOffload -InterfaceDescription <String[]> [-IncludeHidden]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterEncapsulatedPacketTaskOffload** cmdlet gets the network adapters that support encapsulated task offload.
Encapsulated task offload allows the network adapter to perform offload operations such as large send offload (LSO) and virtual machine queue (VMQ) on the inner header for encapsulated packets.

## EXAMPLES

### Example 1: Get the encapsulated packet task offload properties from all network adapters
```
PS C:\> Get-NetAdapterEncapsulatedPacketTaskOffload -Name "*"
```

This command gets all of the encapsulated packet task offload properties from all capable network adapters.

### Example 2: Get the encapsulated packet task offload properties for the specified network adapter
```
PS C:\> Get-NetAdapterEncapsulatedPacketTaskOffload -Name "MyAdapter"
```

This command gets the encapsulated packet task offload properties for the network adapter named MyAdapter.

### Example 3: Get the encapsulated packet task offload properties from network adapters that have it enabled
```
PS C:\> Get-NetAdapterEncapsulatedPacketTaskOffload -Name "*" | Where-Object -FilterScript { $_.Enabled }
```

This command gets the encapsulated packet task offload adapters with encapsulated packet task offload enabled.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter EncapsulatedPacketTaskOffloadSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterEncapsulatedPacketTaskOffload](./Disable-NetAdapterEncapsulatedPacketTaskOffload.md)

[Enable-NetAdapterEncapsulatedPacketTaskOffload](./Enable-NetAdapterEncapsulatedPacketTaskOffload.md)

[Set-NetAdapterEncapsulatedPacketTaskOffload](./Set-NetAdapterEncapsulatedPacketTaskOffload.md)


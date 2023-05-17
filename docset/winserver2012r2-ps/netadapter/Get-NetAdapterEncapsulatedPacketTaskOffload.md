---
external help file: MSFT_NetAdapterEncapsulatedPacketTaskOffload.cdxml-help.xml
Module Name: NetAdapter
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapterencapsulatedpackettaskoffload?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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

### EXAMPLE 1
```
PS C:\>Get-NetAdapterEncapsulatedPacketTaskOffload -Name *
```

This example gets all of the encapsulated packet task offload capable network adapters.

### EXAMPLE 2
```
PS C:\>Get-NetAdapterEncapsulatedPacketTaskOffload -Name MyAdapter
```

This example gets the encapsulated packet task offload properties for the network adapter named MyAdapter.

### EXAMPLE 3
```
PS C:\>Get-NetAdapterEncapsulatedPacketTaskOffload -Name * | Where-Object -FilterScript { $_.Enabled }
```

This example gets the encapsulated packet task offload adapters with encapsulated packet task offload enabled.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specifies both visible and hidden network adapters should be included.
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
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendors of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

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
Specifies the name of the network adapter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter EncapsulatedPacketTaskOffloadSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkID=113423)

[Disable-NetAdapterEncapsulatedPacketTaskOffload](./Disable-NetAdapterEncapsulatedPacketTaskOffload.md)

[Enable-NetAdapterEncapsulatedPacketTaskOffload](./Enable-NetAdapterEncapsulatedPacketTaskOffload.md)

[Set-NetAdapterEncapsulatedPacketTaskOffload](./Set-NetAdapterEncapsulatedPacketTaskOffload.md)


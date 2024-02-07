---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterBinding.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapterbinding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetAdapterBinding
---

# Get-NetAdapterBinding

## SYNOPSIS
Gets a list of bindings for a network adapter.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterBinding [[-Name] <String[]>] [-ComponentID <String[]>] [-DisplayName <String[]>] [-IncludeHidden]
 [-AllBindings] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterBinding -InterfaceDescription <String[]> [-ComponentID <String[]>] [-DisplayName <String[]>]
 [-IncludeHidden] [-AllBindings] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterBinding** cmdlet gets a list of bindings for a network adapter.
By default only the visible bindings shown in the Networking tab under the Network Adapter properties in Windows UI is returned.
To get all properties for a network adapter, use the *AllProperties* parameter.

## EXAMPLES

### Example 1: Get bindings for the specified network adapter
```
PS C:\> Get-NetAdapterBinding -Name "MyAdapter"
```

This command gets the bindings for the network adapter named MyAdapter.

### Example 2: Get all of the binding for the specified network adapter in an unformatted list
```
PS C:\> Get-NetAdapterBinding -Name "MyAdapter" -AllBindings
```

This command gets all of the bindings for the network adapter named MyAdapter as an unformatted list .

### Example 3: Get the state of TCP/IPv4 on the specified network adapter using the display name
```
PS C:\> Get-NetAdapterBinding -Name "MyAdapter" -DisplayName "Internet Protocol Version 4 (TCP/IPv4)"
```

This command gets the state of the TCP/IPv4 on the network adapter named MyAdapter using display name.

### Example 4: Get the state of the TCP/IPv4 transport on the specified network adapter
```
PS C:\> Get-NetAdapterBinding -Name "MyAdapter"  -ComponentID ms_tcpip
```

This command gets the state of the TCP/IPv4 transport on MyAdapter using component ID.

### Example 5: Get the state of TCP/IPv4 and TCP/IPv6 on all visible network adapters using a search string
```
PS C:\> Get-NetAdapterBinding -Name "*" -DisplayName "Internet*"
```

This command gets the state of TCP/IPv4 and TCP/IPv6 on all visible network adapters using wildcard characters.

## PARAMETERS

### -AllBindings
Indicates that the cmdlet gets all the bindings for the network adapter.

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

### -ComponentID
Specifies an array of underlying names of the transport or filter in the following form: `ms_xxxx`, such as `ms_tcpip`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies an array of transport or filter names shown in the Networking tab under the network adapter properties in Windows Server® 2012 and later.

```yaml
Type: String[]
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter BindingSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterBinding](./Disable-NetAdapterBinding.md)

[Enable-NetAdapterBinding](./Enable-NetAdapterBinding.md)

[Set-NetAdapterBinding](./Set-NetAdapterBinding.md)


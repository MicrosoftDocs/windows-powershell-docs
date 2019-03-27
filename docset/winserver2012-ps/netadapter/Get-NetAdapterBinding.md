---
external help file: NetAdapter_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: EF6C7427-DD59-4F5F-8176-6CCF551D7824
manager: dansimp
---

# Get-NetAdapterBinding

## SYNOPSIS
Returns a list of bindings for a network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetAdapterBinding [[-Name] <String[]>] [-AllBindings] [-AsJob] [-CimSession <CimSession[]>]
 [-ComponentID <String[]>] [-DisplayName <String[]>] [-IncludeHidden] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetAdapterBinding [-AllBindings] [-AsJob] [-CimSession <CimSession[]>] [-ComponentID <String[]>]
 [-DisplayName <String[]>] [-IncludeHidden] [-ThrottleLimit <Int32>] -InterfaceDescription <String[]>
```

## DESCRIPTION
The **Get-NetAdapterBinding** cmdlet returns a list of bindings for a network adapter.
By default only the visible bindings shown in the Networking tab under the Network Adapter properties in Windows UI is returned.
To get all properties for a network adapter, use the **AllProperties** parameter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetAdapterBinding -Name MyAdapter
```

This example gets the bindings for the network adapter named MyAdapter.

### EXAMPLE 2
```
PS C:\>Get-NetAdapterBinding -Name MyAdapter -AllBindings
```

This example gets all of the bindings for the network adapter named MyAdapter (unformatted).

### EXAMPLE 3
```
PS C:\>Get-NetAdapterBinding -Name MyAdapter -DisplayName "Internet Protocol Version 4 (TCP/IPv4)"
```

This example gets the state of the TCP/IPv4 on the network adapter named MyAdapter using display name.

### EXAMPLE 4
```
PS C:\>Get-NetAdapterBinding -Name MyAdapter -ComponentID ms_tcpip
```

This example gets the state of the TCP/IPv4 transport on MyAdapter using component ID.

### EXAMPLE 5
```
PS C:\>Get-NetAdapterBinding -Name * -DisplayName "Internet*"
```

This example gets the state of TCP/IPv4 and TCP/IPv6 on all visible adapters using wildcard characters.

## PARAMETERS

### -AllBindings
Returns all the bindings for the network adapter.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComponentID
Specifies the underlying name of the transport or filter in the following form. 

 - `ms_xxxx`, such as `ms_tcpip`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -DisplayName
Specifies the transport or filter name shown in the Networking tab under the network adapter properties in Windows Server® 2012 and later.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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


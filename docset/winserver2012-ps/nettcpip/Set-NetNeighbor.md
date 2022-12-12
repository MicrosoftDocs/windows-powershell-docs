---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/set-netneighbor?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetNeighbor

## SYNOPSIS
Modifies a neighbor cache entry.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetNeighbor [[-IPAddress] <String[]>] [-AddressFamily <AddressFamily[]>] [-AsJob]
 [-CimSession <CimSession[]>] [-InterfaceAlias <String[]>] [-InterfaceIndex <UInt32[]>]
 [-LinkLayerAddress <String>] [-PassThru] [-PolicyStore <String>] [-State <State[]>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetNeighbor [-AsJob] [-CimSession <CimSession[]>] [-LinkLayerAddress <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetNeighbor** cmdlet modifies a neighbor cache entry for IPv4 or IPv6.
The neighbor cache maintains a list of information for each on-link neighbor, including the IP address and the associated link-layer address.
It is only possible to modify neighbor cache entries in a permanent state on interfaces that have link-layer addresses.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetNeighbor -InterfaceIndex 12 -IPAddress 192.168.0.5 -MACaddress 00-00-12-00-00-ff


This cmdlet is an alternative method.
PS C:\>Get-NetNeighbor -InterfaceIndex 12 -IPAddress 192.168.0.5 | Set-NetNeighbor -MACAddress 00-00-12-00-00-ff
```

This example sets a neighbor cache entry with a specific IP address, and updates, or sets, the MAC address property.

## PARAMETERS

### -AddressFamily
Modifies an IP address family of the neighbor cache entry.
This property is automatically generated if unspecified.
The acceptable values for this parameter are:

 -- IPv4: IPv4 address information. 

 -- IPv6: IPv6 address information.

```yaml
Type: AddressFamily[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -IPAddress
Specifies the IP address of the neighbor cache entry.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkLayerAddress
Specifies the link layer address of the neighbor cache entry.
This is also known as a MAC address.
A link-layer address that uses IPv4 address syntax is a tunnel technology that encapsulates packets over an IPv4 tunnel, such as ISATAP or Teredo.
A link-layer address of all zeroes indicates that the neighbor is unreachable and the neighbor cache entry does not have a link-layer address entry.
An empty link-layer address indicates that the link layer does not use link-layer addresses, such as on a loopback interface.

```yaml
Type: String
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the interface to which the neighbor is connected, using InterfaceAlias.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the interface to which the neighbor is connected, using InterfaceIndex.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
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

### -PolicyStore
Specifies the PolicyStore value.
The acceptable values for this parameter are:

 -- ActiveStore: The IP address information is currently valid. 

 -- PersistentStore: The IP address information is persistent across reboots.
When the computer starts, the PersistentStore settings are copied to the ActiveStore. 

The default value is ActiveStore.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies the state of the neighbor cache entry.
It is only possible to modify neighbor cache entries that are in a permanent state.

```yaml
Type: State[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNeighbor
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetNeighbor](./Get-NetNeighbor.md)

[New-NetNeighbor](./New-NetNeighbor.md)

[Remove-NetNeighbor](./Remove-NetNeighbor.md)


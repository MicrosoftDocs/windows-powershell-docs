---
external help file: NetWNV_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 9E327856-C0B0-47E5-8127-A4DFB7FFD3A5
manager: dansimp
---

# Remove-NetVirtualizationProviderRoute

## SYNOPSIS
Removes physical network routes for a virtualized network.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetVirtualizationProviderRoute [-AsJob] [-CimSession <CimSession[]>] [-DestinationPrefix <String[]>]
 [-InterfaceIndex <UInt32[]>] [-Metric <UInt32[]>] [-NextHop <String[]>] [-PassThru] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetVirtualizationProviderRoute [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Remove-NetVirtualizationProviderRoute** cmdlet removes physical network routes for a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
This cmdlet removes Provider Routes that Network Virtualization uses to direct network traffic on the physical network.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can use the Get-NetVirtualizationProviderRoute cmdlet to get routes to delete, or you can specify Provider Routes by using any combination of the following: 

- Destination. 
- Interface. 
- Metric. 
- Next hop gateway.

## EXAMPLES

### Example 1: Remove all Provider Routes
```
PS C:\> Remove-NetVirtualizationProviderRoute
```

This command removes all the Provider Routes for a hv_win8_2 host.

### Example 2: Remove Provider Routes for a specified interface
```
PS C:\>Remove-NetVirtualizationProviderRoute -InterfaceIndex 12
```

This command removes Provider Routes for an interface that has an index of 12.

### Example 3: Remove Provider Routes
```
PS C:\>Remove-NetVirtualizationProviderRoute -DestinationPrefix "0.0.0.0/0" -NextHop "10.1.1.1" -InterfaceIndex 22
```

This command removes a Provider Route for the specified interface, for all network addresses that has the specified next hop value.

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

### -DestinationPrefix
Specifies an array of IP prefixes, as strings, for destination networks.
You can specify IPv4 and IPv6 addresses.
Use prefix notation: **0.0.0.0/0**.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -InterfaceIndex
Specifies an array of indexes for network interfaces that have hv_win8_2 Network Virtualization enabled.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metric
Specifies an array of integer values.
Network Virtualization selects the route with the lowest metric value from a group of usable routes.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHop
Specifies an array of IP addresses for next hop gateways.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationProviderRoute](./Get-NetVirtualizationProviderRoute.md)

[New-NetVirtualizationProviderRoute](./New-NetVirtualizationProviderRoute.md)

[Set-NetVirtualizationProviderRoute](./Set-NetVirtualizationProviderRoute.md)


---
external help file: NetWNV_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: BC4274F1-F6DC-4344-9A1B-DC68163248B0
manager: dansimp
---

# Get-NetVirtualizationProviderRoute

## SYNOPSIS
Gets physical network routes for a virtualized network.

## SYNTAX

```
Get-NetVirtualizationProviderRoute [-AsJob] [-CimSession <CimSession[]>] [-DestinationPrefix <String[]>]
 [-InterfaceIndex <UInt32[]>] [-Metric <UInt32[]>] [-NextHop <String[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetVirtualizationProviderRoute** cmdlet gets physical network routes for a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
Network Virtualization uses Provider Routes to direct network traffic on the physical network.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can specify Provider Routes by using any combination of the following: 

- Destination. 
- Interface. 
- Metric. 
- Next hop gateway.

## EXAMPLES

### Example 1: Get provider routes for a specified interface
```
PS C:\> Get-NetVirtualizationProviderRoute -InterfaceIndex 21
```

This command gets the provider routes for the interface that has the interface index 21.

### Example 2: Get provider routes for destination prefix
```
PS C:\>Get-NetVirtualizationProviderRoute -DestinationPrefix "172.16.0.0/16"
```

This command gets the provider routes that have the specified destination prefix.

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InterfaceIndex
Specifies an array of indexes for network interfaces that have hv_win8_2 Network Virtualization enabled.

```yaml
Type: UInt32[]
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

## OUTPUTS

## NOTES

## RELATED LINKS

[New-NetVirtualizationProviderRoute](./New-NetVirtualizationProviderRoute.md)

[Remove-NetVirtualizationProviderRoute](./Remove-NetVirtualizationProviderRoute.md)

[Set-NetVirtualizationProviderRoute](./Set-NetVirtualizationProviderRoute.md)


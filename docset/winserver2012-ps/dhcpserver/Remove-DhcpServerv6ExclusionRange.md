---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 3483D9F7-DF27-435F-921B-0C5AE0FAD91E
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Remove-DhcpServerv6ExclusionRange

## SYNOPSIS
Deletes a range of IPv6 addresses previously excluded from an IPv6 scope.

## SYNTAX

```
Remove-DhcpServerv6ExclusionRange [-Prefix] <IPAddress> [[-StartRange] <IPAddress>] [[-EndRange] <IPAddress>]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-Passthru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
Deletes a range of IPv6 addresses previously excluded from an IPv6 scope.
If the **StartRange** and **EndRange** parameters are specified, then the exclusion range with the specified starting range and ending range values is deleted.
If only the **StartRange** parameter is specified, then the exclusion range with specified starting range is deleted.
If only the **EndRange** parameter is specified, then the exclusion range with specified ending range is deleted.
If neither the **StartRange** nor **EndRange** parameter is specified, then all of the excluded IP address ranges present in the specified scope are removed.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DhcpServerv6ExclusionRange -Prefix 2001:4898:7020:1020:: -StartRange 2001:4898:7020:1020::1 -EndRange 2001:4898:7020:1020::10
```

This example deletes the excluded IPv6 address range from 2001:4898:7020:1020::1 to 2001:4898:7020:1020::10 from DHCPv6 scope 2001:4898:7020:1020:: on the DHCP server service running on the local computer.

### EXAMPLE 2
```
PS C:\>Remove-DhcpServerv6ExclusionRange -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -StartRange 2001:4898:7020:1020::1
```

This example deletes the IPv6 address range starting from 2001:4898:7020:1020::1 from DHCPv6 scope 2001:4898:7020:1020:: on the DHCP server service running on computer named dhcpserver.contoso.com.

### EXAMPLE 3
```
PS C:\>Remove-DhcpServerv6ExclusionRange -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -EndRange 2001:4898:7020:1020::10
```

This example deletes the IPv6 address range with ending IP address of 2001:4898:7020:1020::10 from DHCPv6 scope 2001:4898:7020:1020:: on the DHCP server service running on computer named dhcpserver.contoso.com.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the Dynamic Host Configuration Protocol (DHCP) server service.

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

### -EndRange
Specifies the ending IPv6 address of the excluded IP range being deleted.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
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

### -Prefix
Specifies the IPv6 subnet prefix of the scope from which the excluded IP ranges is deleted.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartRange
Specifies the starting IPv6 address of the excluded IPv6 range being deleted.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6ExclusionRange
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6ExclusionRange[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv6ExclusionRange](./Add-DhcpServerv6ExclusionRange.md)

[Get-DhcpServerv6ExclusionRange](./Get-DhcpServerv6ExclusionRange.md)


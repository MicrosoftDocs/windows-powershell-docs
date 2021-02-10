---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: BB2C6F39-B2E1-4E7E-BC0A-3A75D1D31F1F
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-DhcpServerv4ExclusionRange

## SYNOPSIS
Adds a range of excluded IP addresses for an IPv4 scope.

## SYNTAX

```
Add-DhcpServerv4ExclusionRange [-ScopeId] <IPAddress> [-StartRange] <IPAddress> [-EndRange] <IPAddress>
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Add-DhcpServerv4ExclusionRange** cmdlet adds a range of excluded IP addresses for an IPv4 scope.
The excluded IP addresses are not leased out by the Dynamic Host Configuration Protocol (DHCP) server service to any DHCP client.
The only exception to this is reservation.
If an IP address is reserved, then the same IP address will be leased to the designated client even if it falls within the exclusion range.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-Dhcpserverv4ExclusionRange -ScopeId 10.1.1.0 -StartRange 10.1.1.1 -EndRange 10.1.1.10
```

This example adds excludes the IP address range from 10.1.1.1 through 10.1.1.10 from the scope 10.1.1.0 on the DHCP server service running on the local computer.

### EXAMPLE 2
```
PS C:\>Add-Dhcpserverv4ExclusionRange -ComputerName dhcpserver.contoso.com -ScopeId 20.1.1.0 -StartRange 20.1.1.1 -EndRange 20.1.1.1
```

This example excludes the IP address 20.1.1.1 from the scope 20.1.1.0 on the DHCP server service running on the computer named dhcpserver.contoso.com.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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
The end IP address of the range being excluded.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

### -ScopeId
Specifies the identifier (ID) of the IPv4 scope from which the IP addresses are being excluded.

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
Specifies the starting IP address of the range being excluded.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4ExclusionRange
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4ExclusionRange
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4ExclusionRange](./Get-DhcpServerv4ExclusionRange.md)

[Remove-DhcpServerv4ExclusionRange](./Remove-DhcpServerv4ExclusionRange.md)


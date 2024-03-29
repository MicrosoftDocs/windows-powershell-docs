---
external help file: PS_DhcpServerV6ExclusionRange_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv6exclusionrange?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv6ExclusionRange
---

# Get-DhcpServerv6ExclusionRange

## SYNOPSIS
Gets the IPv6 address ranges excluded from the specified IPv6 subnet prefix.

## SYNTAX

```
Get-DhcpServerv6ExclusionRange [-ComputerName <String>] [[-Prefix] <IPAddress[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv6ExclusionRange** cmdlet gets the IPv6 address ranges excluded from the specified IPv6 subnet prefix.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv6ExclusionRange -ComputerName dhcpserver.contoso.com
```

This example gets all of the IPv6 address ranges which have been excluded from all of the DHCPv6 scopes on the DHCP server service.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv6ExclusionRange -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example gets all of the IPv6 address ranges which have been excluded from the specified DHCPv6 scope.

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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the Dynamic Host Configuration Protocol (DHCP) server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefix
Specifies the IPv6 prefixes of the scopes for which the exclusion ranges are requested.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6ExclusionRange[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv6ExclusionRange](./Add-DhcpServerv6ExclusionRange.md)

[Remove-DhcpServerv6ExclusionRange](./Remove-DhcpServerv6ExclusionRange.md)


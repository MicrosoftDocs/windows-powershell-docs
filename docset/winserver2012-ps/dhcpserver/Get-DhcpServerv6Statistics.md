---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: A85AAD1E-A992-46B1-B836-9B9E3FA52F14
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-DhcpServerv6Statistics

## SYNOPSIS
Gets the Dynamic Host Configuration Protocol (DHCP) server service statistics for IPv6.

## SYNTAX

```
Get-DhcpServerv6Statistics [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv6Statistics** cmdlet gets the Dynamic Host Configuration Protocol (DHCP) server service statistics for IPv6.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv6Statistics -ComputerName dhcpserver.contoso.com
```

This example gets all of the DHCPv6 server service statistics for the DHCP server service running on the computer named dhcpserver.contoso.com.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Statistics
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv6ScopeStatistics{{Provide related cmdlet topic}}](00000000-0000-0000-0000-000000000000)


---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 64D5384C-D67A-459E-8DAF-20C426CAFC09
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-DnsServerEDns

## SYNOPSIS
Gets EDNS configuration settings on a DNS server.

## SYNTAX

```
Get-DnsServerEDns [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DnsServerEDns** cmdlet gets extension mechanisms for DNS (EDNS) configuration settings on a Domain Name System (DNS) server.
This cmdlet gets the EDNS settings for CacheTimeout, EnableProbes, and EnableReception.

## EXAMPLES

### Example 1: Get EDNS settings
```
PS C:\> Get-DnsServerEDns
```

This command gets the EDNS settings on a local DNS server.

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
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerEDns

## NOTES

## RELATED LINKS

[Set-DnsServerEDns](./Set-DnsServerEDns.md)


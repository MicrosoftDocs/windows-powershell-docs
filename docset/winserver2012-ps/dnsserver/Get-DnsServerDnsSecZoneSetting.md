---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 3EC04CE3-FEBF-4DE6-83A3-5DFC5091029B
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-DnsServerDnsSecZoneSetting

## SYNOPSIS
Gets DNSSEC settings for a zone.

## SYNTAX

```
Get-DnsServerDnsSecZoneSetting [-ZoneName] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DnsServerDnsSecZoneSetting** cmdlet gets the Domain Name System Security Extensions (DNSSEC) settings for a zone on a Domain Name System (DNS) server.

## EXAMPLES

### Example 1: Get DNSSEC settings
```
PS C:\> Get-DnsServerDnsSecZoneSetting -ZoneName "western.contoso.com"
```

This command gets the DNS Security Extensions for the zone named western.contoso.com.

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
Specifies a DNS server.
If you do not specify this parameter, the command runs on the local system.
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

### -ZoneName
Specifies an array of names of DNS zones.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDnsSecZoneSetting[]

## NOTES

## RELATED LINKS

[Set-DnsServerDnsSecZoneSetting](./Set-DnsServerDnsSecZoneSetting.md)

[Test-DnsServerDnsSecZoneSetting](./Test-DnsServerDnsSecZoneSetting.md)


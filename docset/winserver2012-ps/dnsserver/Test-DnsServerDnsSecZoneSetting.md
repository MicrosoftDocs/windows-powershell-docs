---
author: Kateyanne
external help file: DnsServer_Cmdlets.xml
manager: dansimp
Module Name: DnsServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dnsserver/test-dnsserverdnsseczonesetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Test-DnsServerDnsSecZoneSetting

## SYNOPSIS
Validates DNSSEC settings for a zone.

## SYNTAX

```
Test-DnsServerDnsSecZoneSetting [-ZoneName] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Test-DnsServerDnsSecZoneSetting** cmdlet validates Domain Name System Security Extensions (DNSSEC) settings for a zone on a Domain Name System (DNS) server.
The cmdlet returns a validation object.

## EXAMPLES

### Example 1: Validate DNSSEC settings
```
PS C:\> Test-DnsServerDnsSecZoneSetting -ZoneName "western.contoso.com"
```

This command validates DNSSEC settings for the zone named western.contoso.com.

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
Specifies the name of a DNS zone.

```yaml
Type: String
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerZoneDnsSecValidationResult

## NOTES

## RELATED LINKS

[Get-DnsServerDnsSecZoneSetting](./Get-DnsServerDnsSecZoneSetting.md)

[Set-DnsServerDnsSecZoneSetting](./Set-DnsServerDnsSecZoneSetting.md)


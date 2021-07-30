---
external help file: PS_DnsServerCache_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/dnsserver/get-dnsservercache?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerCache
---

# Get-DnsServerCache

## SYNOPSIS
Retrieves DNS server cache settings.

## SYNTAX

```
Get-DnsServerCache [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerCache** cmdlet retrieves the following Domain Name System (DNS) server cache settings: MaxTTL, MaxNegativeTTL, MaxKBSize, EnablePollutionProtection, LockingPercent, StoreEmptyAuthenticationResponse.

## EXAMPLES

### Example 1: Get DNS server cache properties
```
PS C:\>Get-DnsServerCache -ComputerName "Win12S-05.DNSServer-01.Contoso.com"
MaxTTL                           : 1.00:00:00

MaxNegativeTTL                   : 00:15:00

MaxKBSize                        : 10240

EnablePollutionProtection        : True

LockingPercent                   : 100

StoreEmptyAuthenticationResponse : True
```

This command gets DNS server cache properties on a DNS server that has an FQDN of Win12S-05.DNSServer-01.Contoso.com.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specifies a DNS server.
The acceptable values for this parameter are:: an IP V4 address; an IP V6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerCache

## NOTES

## RELATED LINKS

[Clear-DnsServerCache](./Clear-DnsServerCache.md)

[Set-DnsServerCache](./Set-DnsServerCache.md)

[Show-DnsServerCache](./Show-DnsServerCache.md)


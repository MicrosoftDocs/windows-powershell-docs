---
external help file: PS_DnsServerEncryptionProtocol_v1.0.0.cdxml-help.xml
Module Name: DnsServer
online version:
schema: 2.0.0
---

# Get-DnsServerEncryptionProtocol

## SYNOPSIS
Retrieves DNS server encryption protocol settings.

## SYNTAX

```
Get-DnsServerEncryptionProtocol [-ComputerName <String>] [-PassThru <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The Get-DnsServerEncryptionProtocol cmdlet retrieves Domain Name System (DNS) server encryption settings. This cmdlet shows:

- DNS over HTTPS (DoH) encryption status (enabled or disabled)
- Specifies the URI template(s) for DNS over HTTPS (DoH) requests

When DoH is enabled, DNS queries are encrypted using HTTPS to provide enhanced security for DNS communications. Multiple URI templates can be configured to provide redundancy and load distribution across DoH endpoints.

## EXAMPLES

### Example 1: Retrieve encryption settings from local DNS server
```powershell
PS C:\> Get-DnsServerEncryptionProtocol

EnableDoh   : True
UriTemplate : https://dnsserver.example.com/dns-query|https://backup.example.com/dns-query
```

This command retrieves the current encryption settings from the local DNS server. The output shows that DNS over HTTPS (DoH) is enabled with multiple URI templates configured for redundancy. Templates are displayed pipe-separated.

### Example 2: Retrieve encryption settings from remote DNS server
```powershell
PS C:\> Get-DnsServerEncryptionProtocol -ComputerName "dns1.contoso.com"

EnableDoh   : False
UriTemplate :
```

This command retrieves the encryption settings from a remote DNS server. The output shows that DoH is currently disabled and no URI template is configured.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt. You can continue to work in the session while the job completes. To manage the job, use the `*-Job` cmdlets. To get the job results, use the Receive-Job cmdlet.

For more information about Windows PowerShell background jobs, see about_Jobs.

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
Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session object, such as the output of a New-CimSession or Get-CimSession cmdlet. The default is the current session on the local computer.

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
Specifies a DNS server. The acceptable values for this parameter are: an IPv4 address; an IPv6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -PassThru
Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer. The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Boolean

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DnsServerEncryptionProtocol

## NOTES
- The DNS server must be running Windows Server 2025 or later to support encryption settings.
- When EnableDoh is false, the URI Template will be empty.
- This cmdlet can be used to verify DoH configuration before and after making changes.

## RELATED LINKS

[Set-DnsServerEncryptionProtocol](Set-DnsServerEncryptionProtocol.md)

[DNS over HTTPS (DoH)](https://learn.microsoft.com/windows-server/networking/dns/dns-over-https)

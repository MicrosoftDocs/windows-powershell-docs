---
external help file: PS_DnsServerEncryptionProtocol_v1.0.0.cdxml-help.xml
Module Name: DnsServer
online version:
schema: 2.0.0
---

# Set-DnsServerEncryptionProtocol

## SYNOPSIS
Configures DNS server encryption protocol settings.

## SYNTAX

```
Set-DnsServerEncryptionProtocol -EnableDoh <Boolean> [-UriTemplate <String>] [-ComputerName <String>]
 [-Force <Boolean>] [-PassThru <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-DnsServerEncryptionProtocol cmdlet modifies encryption settings on a Domain Name System (DNS) server. You can use this cmdlet to:

- Enable or disable DNS over HTTPS (DoH) protocol
- Configure single or multiple URI templates for DoH requests

After modifying encryption settings, you must restart the DNS Server service for changes to take effect.

When DoH is enabled, DNS queries are encrypted using HTTPS to provide enhanced security for DNS communications. Multiple URI templates provide redundancy and load distribution.

## EXAMPLES

### Example 1: Enable DoH with a single URI template
```powershell
PS C:\> Set-DnsServerEncryptionProtocol -EnableDoh $true -UriTemplate "https://dns.example.com/dns-query"
PS C:\> Restart-Service DNS
```

This command enables DNS over HTTPS (DoH) on the DNS server with the specified URI template. The DNS service must be restarted for the changes to take effect.

### Example 2: Enable DoH with multiple URI templates
```powershell
PS C:\> Set-DnsServerEncryptionProtocol -EnableDoh $true -UriTemplate "https://primary.example.com/dns-query|https://backup.example.com/dns-query"
PS C:\> Restart-Service DNS
```

This command configures DoH with multiple URI templates (separated by pipe character) for redundancy and load distribution.

### Example 3: Disable DoH
```powershell
PS C:\> Set-DnsServerEncryptionProtocol -EnableDoh $false
PS C:\> Restart-Service DNS
```

This command disables DNS over HTTPS (DoH) on the DNS server. The URI template configuration is cleared when DoH is disabled.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableDoh
Specifies whether to enable or disable DNS over HTTPS (DoH) on the DNS server. Set to `$true` to enable DoH, or `$false` to disable it. When disabled, any configured URI templates are cleared.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation. Use this parameter to bypass confirmation prompts when scripting or automating cmdlet execution.

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

### -UriTemplate
Specifies one or more URI templates for DNS over HTTPS (DoH) requests. 

- For a single template: `"https://dns.example.com/dns-query"`
- For multiple templates (redundancy/load balancing): `"https://primary.example.com/dns-query|https://backup.example.com/dns-query"`
- Templates must be valid HTTPS URIs compliant with RFC 3986
- DoH implementation follows RFC 8484 (DNS Queries over HTTPS) specification
- Multiple templates are separated by the pipe character (|)
- This parameter is required when EnableDoh is set to `$true`

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DnsServerEncryptionProtocol

## NOTES
- After modifying encryption settings, you must restart the DNS Server service for changes to take effect.
- When enabling DoH, ensure that the SSL/TLS certificate is properly configured for the specified URI template.
- The DNS server must be running Windows Server 2025 or later.
- The UriTemplate parameter is required when EnableDoh is set to `$true`.
- Multiple URI templates provide redundancy and load distribution.

## RELATED LINKS

[Get-DnsServerEncryptionProtocol](Get-DnsServerEncryptionProtocol.md)

[DNS over HTTPS (DoH)](https://learn.microsoft.com/windows-server/networking/dns/dns-over-https)

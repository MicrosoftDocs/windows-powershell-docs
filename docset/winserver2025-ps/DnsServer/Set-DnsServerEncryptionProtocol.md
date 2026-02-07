---
Learn how to enable or disable DNS over HTTPS (DoH) and configure URI templates for secure DNS queries using the Set-DnsServerEncryptionProtocol cmdlet.
external help file: PS_DnsServerEncryptionProtocol_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 01/14/2026
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverencryptionprotocol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerEncryptionProtocol
---

# Set-DnsServerEncryptionProtocol

## SYNOPSIS
Configures DNS server encryption protocol settings for DNS over HTTPS (DoH) on Windows Server 2025
or later.

## SYNTAX

```
Set-DnsServerEncryptionProtocol -EnableDoh <Boolean> [-UriTemplate <String>] [-ComputerName <String>]
 [-Force] [-PassThru <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-DnsServerEncryptionProtocol` cmdlet modifies encryption settings on a Domain Name System
(DNS) server to enable or disable DNS over HTTPS (DoH) and configure URI templates for DNS
queries. When DoH is enabled, DNS queries are encrypted over HTTPS, protecting them from
eavesdropping and tampering.

You must restart the DNS Server service for changes to take effect. Ensure that a valid SSL/TLS
certificate is configured for the DNS server with the hostname(s) specified in the URI template(s).

> [!IMPORTANT]
> The `Set-DnsServerEncryptionProtocol` cmdlet is available on Windows Server 2025 or
> later beginning with 2026-02 Security Update.

## EXAMPLES

### Example 1: Enable DNS over HTTPS (DoH) with default URI template

```powershell
Set-DnsServerEncryptionProtocol -EnableDoh $true
```

```Output
WARNING: Modifying DOH setting will require restarting the DNS service.
```

```powershell
Restart-Service DNS
```

In this example, the command enables DNS over HTTPS (DoH). When you don't specify the **UriTemplate** parameter, the DNS server automatically generates a URI template based on the server's FQDN with the `/dns-query` path (for example, `https://dnsserver.contoso.com/dns-query`). The DNS service must be restarted for the changes to take effect.

### Example 2: Enable DNS over HTTPS (DoH) with a single URI template

```powershell
Set-DnsServerEncryptionProtocol -EnableDoh $true -UriTemplate "https://dnsserver.example.net/dns-query"
```

```Output
WARNING: Modifying DOH setting will require restarting the DNS service.
```

```powershell
Restart-Service DNS
```

In this example, the command enables DNS over HTTPS (DoH) on the DNS server with the specified URI template.
The DNS service must be restarted for the changes to take effect.

### Example 3: Enable DNS over HTTPS (DoH) with multiple URI templates

```powershell
Set-DnsServerEncryptionProtocol -EnableDoh $true -UriTemplate "https://dnsserver.example.net/dns-query|https://dnsserver2.example.net/dns-query"
```

```Output
WARNING: Modifying DOH setting will require restarting the DNS service.
```

```powershell
Restart-Service DNS
```

In this example, the command configures DNS over HTTPS (DoH) with multiple URI templates separated by the pipe
character `|`. Multiple URI templates may be provisioned to allow client implementations to choose
among multiple DoH endpoints. A maximum of three URI templates can be specified. The DNS service
must be restarted for the changes to take effect.

### Example 4: Disable DNS over HTTPS (DoH)

```powershell
Set-DnsServerEncryptionProtocol -EnableDoh $false
```

```Output
WARNING: Modifying DOH setting will require restarting the DNS service.
```

```powershell
Restart-Service DNS
```

In this example, the command disables DNS over HTTPS (DoH) on the DNS server. When DoH is disabled, all configured
URI templates are automatically cleared. The DNS service must be restarted for the changes to take effect.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt. You can continue to work in the session while the job completes. To manage the job, use the `*-Job` cmdlets. To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

Specifies a DNS server. The acceptable values for this parameter are:

- An IP V4 address
- An IP V6 address
- Any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host
  name, or NETBIOS name.


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

Specifies whether to enable or disable DNS over HTTPS (DoH) on the DNS server. Set the value to `$true` to
enable DoH, or `$false` to disable it. When disabled, any configured URI templates are also cleared.

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

Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you are working.

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

Specifies one or more URI templates for DNS over HTTPS (DoH) queries.

URI template(s) must be valid HTTPS URIs compliant with [RFC 3986, Uniform Resource Identifier (URI):
Generic Syntax](https://datatracker.ietf.org/doc/html/rfc3986). Ensure that a valid SSL/TLS certificate is
configured for the DNS server with the hostname(s) specified in the URI template(s).

For a single URI template, specify a valid HTTPS URI (for example, `"https://dnsserver.example.net/dns-query"`).
For multiple URI templates, separate them with the pipe character `|` (for example,
`"https://dnsserver.example.net/dns-query|https://dnsserver2.example.net/dns-query"`).
Multiple URI templates may be provisioned to allow client implementations to choose among multiple
DoH endpoints. A maximum of three URI templates can be specified.

If you don't specify a value when **EnableDoh** is set to `$true`, the DNS server automatically generates a 
URI template using the format `https://<server-fqdn>/dns-query`, where `<server-fqdn>` is the server's fully qualified domain name. 
For example, if your DNS server's FQDN is `dns1.contoso.com`, the template will be `https://dns1.contoso.com/dns-query`.


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

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

You cannot pipe objects to this cmdlet.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerEncryptionProtocol

This cmdlet returns a `DnsServerEncryptionProtocol` object that represents the updated encryption protocol settings on the DNS server.

## NOTES

## RELATED LINKS

[Get-DnsServerEncryptionProtocol](./Get-DnsServerEncryptionProtocol.md)
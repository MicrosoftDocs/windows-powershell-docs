---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerEncryptionProtocol_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 01/14/2026
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverencryptionprotocol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerEncryptionProtocol
---

# Set-DnsServerEncryptionProtocol

## SYNOPSIS
Configures DNS server encryption protocol settings.

## SYNTAX

```
Set-DnsServerEncryptionProtocol -EnableDoh <Boolean> [-UriTemplate <String>] [-ComputerName <String>]
 [-Force] [-PassThru <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerEncryptionProtocol** cmdlet modifies encryption settings on a Domain Name System (DNS) server to enable or disable DNS over HTTPS (DoH) protocol and configure URI templates for DNS queries. When DoH is enabled, DNS queries are encrypted over HTTPS, protecting them from eavesdropping and tampering. After modifying encryption settings, you must restart the DNS Server service for changes to take effect. Ensure that a valid SSL/TLS certificate is configured for the DNS server with the hostname(s) specified in the URI template(s). This cmdlet is available on Windows Server 2025 or later.

## EXAMPLES

### Example 1: Enable DNS over HTTPS (DoH) with default URI template
```powershell
PS C:\> Set-DnsServerEncryptionProtocol -EnableDoh $true
PS C:\> Restart-Service DNS
```

This command enables DNS over HTTPS (DoH) using the default URI template path `/dns-query`. When you don't specify the **UriTemplate** parameter, the DNS server uses a template based on the server's FQDN with the standard `/dns-query` path (for example, `https://dnsserver.contoso.com/dns-query`).

### Example 2: Enable DNS over HTTPS (DoH) with a single URI template
```powershell
PS C:\> Set-DnsServerEncryptionProtocol -EnableDoh $true -UriTemplate "https://dnsserver.example.net/dns-query"
PS C:\> Restart-Service DNS
```

This command enables DNS over HTTPS (DoH) on the DNS server with the specified URI template. The DNS service must be restarted for the changes to take effect.

### Example 3: Enable DNS over HTTPS (DoH) with multiple URI templates
```powershell
PS C:\> Set-DnsServerEncryptionProtocol -EnableDoh $true -UriTemplate "https://dnsserver.example.net/dns-query|https://dnsserver2.example.net/dns-query"
PS C:\> Restart-Service DNS
```

This command configures DNS over HTTPS (DoH) with multiple URI templates separated by the pipe character (|) for redundancy and load distribution. A maximum of three URI templates can be specified.

### Example 4: Disable DNS over HTTPS (DoH)
```powershell
PS C:\> Set-DnsServerEncryptionProtocol -EnableDoh $false
PS C:\> Restart-Service DNS
```

This command disables DNS over HTTPS (DoH) on the DNS server. All configured URI templates are automatically cleared.

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
Specifies one or more URI templates for DNS over HTTPS (DoH) queries. If not specified when **EnableDoh** is set to `$true`, the DNS server uses a default URI template with the `/dns-query` path based on the server's fully qualified domain name (FQDN).

For a single URI template, specify `"https://dnsserver.example.net/dns-query"`. To provide multiple URI templates for redundancy and load balancing, specify them as **a single string** with templates separated by the pipe character (|): `"https://dnsserver.example.net/dns-query|https://dnsserver2.example.net/dns-query"`. A maximum of three URI templates can be specified.

URI templates must be valid HTTPS URIs compliant with [RFC 3986, Uniform Resource Identifier (URI): Generic Syntax](https://datatracker.ietf.org/doc/html/rfc3986). Ensure that a valid SSL/TLS certificate is configured for the DNS server with the hostname(s) specified in the URI template(s).


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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerEncryptionProtocol

## NOTES

## RELATED LINKS

[Get-DnsServerEncryptionProtocol](./Get-DnsServerEncryptionProtocol.md)
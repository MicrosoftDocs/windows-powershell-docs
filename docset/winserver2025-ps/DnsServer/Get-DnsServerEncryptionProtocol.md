---
description: Learn how to retrieve DNS over HTTPS (DoH) settings using the Get-DnsServerEncryptionProtocol cmdlet in Windows PowerShell for Windows Server 2025 and later.
external help file: PS_DnsServerEncryptionProtocol_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 01/14/2026
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverencryptionprotocol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerEncryptionProtocol
---

# Get-DnsServerEncryptionProtocol

## SYNOPSIS
Retrieves DNS server encryption protocol settings for DNS over HTTPS (DoH) on Windows Server 2025 or later.

## SYNTAX

```
Get-DnsServerEncryptionProtocol [-ComputerName <String>] [-PassThru <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-DnsServerEncryptionProtocol` cmdlet can be used to verify the current DoH configuration
on a DNS server. The cmdlet retrieves the current settings as an object with the properties
**EnableDoh** and **UriTemplate** to indicate whether DoH is enabled and the configured URI
templates for DNS queries over HTTPS.

> [!IMPORTANT]
> The `Get-DnsServerEncryptionProtocol` cmdlet is available on Windows Server 2025 or
> later beginning with 2026-02 Security Update.

## EXAMPLES

### Example 1: Retrieve encryption settings from local DNS server

In this example, the command retrieves the current encryption settings from the local DNS server.

```powershell
Get-DnsServerEncryptionProtocol
```

```Output
EnableDoh   : True
UriTemplate : https://dnsserver.example.net/dns-query
```

The output shows that DNS over HTTPS (DoH) is enabled with a configured URI template.

### Example 2: Retrieve encryption settings from remote DNS server

In this example, the command retrieves the encryption settings from a remote DNS server named
"dns1.contoso.com".

```powershell
Get-DnsServerEncryptionProtocol -ComputerName "dns1.contoso.com"
```

```Output
EnableDoh   : False
UriTemplate :
```

The output shows that DNS over HTTPS (DoH) is currently disabled for the specified remote DNS
server.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

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

Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

[Set-DnsServerEncryptionProtocol](./Set-DnsServerEncryptionProtocol.md)

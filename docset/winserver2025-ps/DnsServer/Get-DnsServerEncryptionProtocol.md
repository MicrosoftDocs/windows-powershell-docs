---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerEncryptionProtocol_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 01/14/2026
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverencryptionprotocol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerEncryptionProtocol
---

# Get-DnsServerEncryptionProtocol

## SYNOPSIS
Retrieves DNS server encryption protocol settings. This cmdlet is available on Windows Server 2025 or later.

## SYNTAX

```
Get-DnsServerEncryptionProtocol [-ComputerName <String>] [-PassThru <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The **Get-DnsServerEncryptionProtocol** cmdlet retrieves Domain Name System (DNS) server DNS over HTTPS (DoH) settings: **EnableDoh** and **UriTemplate**.

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

Specifies a DNS server.
The acceptable values for this parameter are: an IP V4 address; an IP V6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

Returns an object representing the item with which you are working. By default, this cmdlet doesn't generate any output.

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

## NOTES

## RELATED LINKS

[Set-DnsServerEncryptionProtocol](./Set-DnsServerEncryptionProtocol.md)

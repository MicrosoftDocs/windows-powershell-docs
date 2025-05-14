---
description: The Get-DnsClientDohServerAddress cmdlet gets the DNS-over-HTTPS (DoH) server configuration from the supported DoH servers.
external help file: MSFT_DnsClientDohServerAddress.cdxml-help.xml
Module Name: DnsClient
ms.date: 08/31/2021
online version: https://learn.microsoft.com/powershell/module/dnsclient/get-dnsclientdohserveraddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsClientDohServerAddress
---

# Get-DnsClientDohServerAddress

## SYNOPSIS
Gets the DoH server configuration.

## SYNTAX

```
Get-DnsClientDohServerAddress [[-ServerAddress] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsClientDohServerAddress** cmdlet gets the DNS-over-HTTPS (DoH) server configuration for supported DoH servers.
If you don't specify a server, the command displays all supported DoH servers.

## EXAMPLES

### Example 1: Get configuration for all DoH servers
```powershell
Get-DnsClientDohServerAddress
```

This example gets configuration for all supported DoH servers.

### Example 2: Get configuration for specific DoH servers
```powershell
Get-DnsClientDohServerAddress -ServerAddress 10.23.1.1,10.18.1.1
```

This example gets DoH configuration for the servers 10.23.1.1 and 10.18.1.1.

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

### -ServerAddress
Specifies the IP addresses for which to retrieve the system DoH configuration.
Addresses must be present in the system list for the command to succeed.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_DNSClientDohServerAddress

## NOTES

## RELATED LINKS

[Add-DnsClientDohServerAddress](Add-DnsClientDohServerAddress.md)

[Add-DnsClientNrptRule](Add-DnsClientNrptRule.md)

[Remove-DnsClientDohServerAddress](Remove-DnsClientDohServerAddress.md)

[Set-DnsClientDohServerAddress](Set-DnsClientDohServerAddress.md)

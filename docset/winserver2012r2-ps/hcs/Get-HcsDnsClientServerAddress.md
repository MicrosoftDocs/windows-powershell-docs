---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/hcs/get-hcsdnsclientserveraddress?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HcsDnsClientServerAddress
---

# Get-HcsDnsClientServerAddress

## SYNOPSIS
Gets the server addresses that a Domain Name System (DNS) client device is configured to use.

## SYNTAX

```
Get-HcsDnsClientServerAddress [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsDnsClientServerAddress** cmdlet gets the server addresses that a DNS client device is configured to use.

## EXAMPLES

### Example 1: Get the server addresses of a DNS client
```
PS C:\> Get-HcsDnsClientServerAddress


PrimaryIPv4                   PrimaryIPv6                   SecondaryIPv4                 SecondaryIPv6
-----------                   -----------                   -------------                 -------------
192.168.200.239                                            {192.168.10.29, 192.168.10.28} {}
```

This command gets the server addresses of a DNS client.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Powershell.Cmdlets.DnsInfo
The return object has four properties:

- Primary DNS address (an IPAddress) 
- Secondary DNS addresses (an array of IPAddress)

The DnsInfo object has the following properties:

- DnsInfo: PrimaryIPv4 = platInfo.PrimaryIPv4;  PrimaryIPv6 = platInfo.PrimaryIPv6;  SecondaryIPv4 = platInfo.SecondaryIPv4.ToArray();SecondaryIPv6 = platInfo.SecondaryIPv6.ToArray();
- IPAddress PrimaryIPv4 
- IPAddress PrimaryIPv6 
- IPAddress\[\] SecondaryIPv4 
- IPAddress\[\] SecondaryIPv6

## NOTES

## RELATED LINKS

[Set-HcsDnsClientServerAddress](./Set-HcsDnsClientServerAddress.md)


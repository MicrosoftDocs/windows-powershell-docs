---
author: Kateyanne
description: 
external help file: PS_DnsServerTrustAnchor_v1.0.0.cdxml-help.xml
manager: jasgro
Module Name: DnsServer
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/dnsserver/get-dnsservertrustanchor?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerTrustAnchor
---

# Get-DnsServerTrustAnchor

## SYNOPSIS
Gets trust anchors on a DNS server.

## SYNTAX

```
Get-DnsServerTrustAnchor [-ComputerName <String>] [-Name] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerTrustAnchor** cmdlet gets trust anchors on a DNS server.
If you do not specify the name of a trust anchor to get, the cmdlet returns all trust anchors.

## EXAMPLES

### Example 1: Get all trust anchors for a trust zone
```
PS C:\> Get-DnsServerTrustAnchor -Name "sec.contoso.com"
```

This command gets the trust anchors for a trust zone named sec.contoso.com.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a remote DNS server.
The acceptable values for this parameter are: an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -Name
Specifies the name of a trust anchor on a DNS server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TrustAnchorName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerTrustAnchor[]

## NOTES

## RELATED LINKS

[Import-DnsServerTrustAnchor](./Import-DnsServerTrustAnchor.md)

[Add-DnsServerTrustAnchor](./Add-DnsServerTrustAnchor.md)

[Remove-DnsServerTrustAnchor](./Remove-DnsServerTrustAnchor.md)


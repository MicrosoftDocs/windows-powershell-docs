---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-HcsDnsClientServerAddress
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: F6BB7980-7F94-44F4-988F-70E618918D40
---

# Set-HcsDnsClientServerAddress

## SYNOPSIS
Sets the server addresses for a Domain Name System (DNS) client device.

## SYNTAX

```
Set-HcsDnsClientServerAddress [-PrimaryIPv4 <IPAddress>] [-PrimaryIPv6 <IPAddress>]
 [-SecondaryIPv4 <IPAddress[]>] [-SecondaryIPv6 <IPAddress[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HcsDnsClientServerAddress** cmdlet sets the server addresses for a DNS client device.

## EXAMPLES

### Example 1: Set the primary DNS address
```
PS C:\> Set-HcsDnsClientServerAddress -PrimaryIPv4 
192.168.200.239

PrimaryIPv4                   PrimaryIPv6                   SecondaryIPv4                 SecondaryIPv6
-----------                   -----------                   -------------                 -------------
192.168.200.239                                             {192.168.10.29, 192.168.10.28}{}
```

This command specifies the **PrimaryIPv4** parameter to set the primary IPv4 DNS server address for a client.

### Example 2: Set the address for two secondary DNS servers
```
PS C:\> Set-HcsDnsClientServerAddress -SecondaryIPv4 
192.168.10.29,192.168.10.28

PrimaryIPv4                   PrimaryIPv6                   SecondaryIPv4                 SecondaryIPv6
-----------                   -----------                   -------------                 -------------
192.68.200.239                                              {192.68.10.29, 192.68.10.28}  {}
```

This command specifies the **SecondaryIPv4** parameter to set two secondary IPv4 DNS server addresses for a client.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryIPv4
Specifies the primary IPv4 server address for a DNS client.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryIPv6
Specifies the primary IPv6 server address for a DNS client.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryIPv4
Specifies an array of secondary IPv4 server addresses for a DNS client.
If the client cannot resolve the primary server, it uses a secondary server address.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryIPv6
Specifies an array of secondary IPv6 server addresses for a DNS client.
If the client cannot resolve the primary server, it uses a secondary server address.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Powershell.Cmdlets.DnsInfo
The DnsInfo object has the following properties:

- IPAddress PrimaryIPv4 
- IPAddress PrimaryIPv6 
- IPAddress\[\] SecondaryIPv4 
- IPAddress\[\] SecondaryIPv6

## NOTES

## RELATED LINKS

[Get-HcsDnsClientServerAddress](./Get-HcsDnsClientServerAddress.md)


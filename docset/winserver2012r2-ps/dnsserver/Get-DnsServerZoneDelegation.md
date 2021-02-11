---
external help file: PS_DnsServerZoneDelegation_v1.0.0.cdxml-help.xml
Module Name: DnsServer
online version: 
schema: 2.0.0
title: Get-DnsServerZoneDelegation
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: F01664CF-1D04-4001-B3A1-A9F86C2A8B19
---

# Get-DnsServerZoneDelegation

## SYNOPSIS
Gets the zone delegations of a DNS server zone.

## SYNTAX

```
Get-DnsServerZoneDelegation [[-ChildZoneName] <String>] [-Name] <String> [-ComputerName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerZoneDelegation** cmdlet gets the zone delegation objects for a Domain Name System (DNS) server zone.
You can specify a child zone name or get all child zones of a zone.

## EXAMPLES

### Example 1: Get delegations from a zone
```
PS C:\> Get-DnsServerZoneDelegation -Name "contoso.com"
```

This command gets all the child zones for zone named contoso.com.
You could pipe the output of this command to related cmdlet instead of viewing the object in the console.

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

### -ChildZoneName
Specifies a name of a child zone.
If you do not specify a name, the cmdlet gets all the child zones for the DNS zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies a DNS server.
If you do not specify this parameter, the command runs on the local system.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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
Specifies the name of a zone.
This is the parent DNS zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ZoneName

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerZoneDelegation[]

## NOTES

## RELATED LINKS

[Add-DnsServerZoneDelegation](./Add-DnsServerZoneDelegation.md)

[Remove-DnsServerZoneDelegation](./Remove-DnsServerZoneDelegation.md)

[Set-DnsServerZoneDelegation](./Set-DnsServerZoneDelegation.md)


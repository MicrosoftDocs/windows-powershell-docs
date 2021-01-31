---
external help file: IpamDiscoveryDomain.cdxml-help.xml
Module Name: IpamServer
online version: 
schema: 2.0.0
title: Get-IpamDiscoveryDomain
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B285F095-9420-4A15-84F4-8C06125E8286
---

# Get-IpamDiscoveryDomain

## SYNOPSIS
Gets the list of Active Directory domains in which IPAM discovers infrastructure servers.

## SYNTAX

```
Get-IpamDiscoveryDomain [[-Name] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamDiscoveryDomain** cmdlet gets the list of Active Directory domains in which IP Address Management (IPAM) discovers infrastructure servers.
You can retrieve the configuration for a particular domain by specifying the fully qualified domain name (FQDN) of that domain.

## EXAMPLES

### Example 1: Get all discovery domains
```
PS C:\> Get-IpamDiscoveryDomain
DomainName                    DiscoverDc                    DiscoverDns                   DiscoverDhcp

----------                    ----------                    -----------                   ------------

contoso.com                   True                          True                          True

minings.com                   False                         True                          True
```

This command gets all discovery domains that are configured in IPAM.

### Example 2: Get a specific discovery domain
```
PS C:\>Get-IpamDiscoveryDomain -Name Contoso.com
DomainName                    DiscoverDc                    DiscoverDns                   DiscoverDhcp

----------                    ----------                    -----------                   ------------

contoso.com                   True                          True                          True
```

This command gets a discovery domain named Contoso.com, which is configured in IPAM.

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

### -Name
Specifies an array of FQDNs in an Active Directory domain to retrieve.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
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

### IpamDiscoveryDomain
Represents an Active Directory domain in which IPAM discovers infrastructure servers.

## NOTES

## RELATED LINKS

[Add-IpamDiscoveryDomain](./Add-IpamDiscoveryDomain.md)

[Remove-IpamDiscoveryDomain](./Remove-IpamDiscoveryDomain.md)

[Set-IpamDiscoveryDomain](./Set-IpamDiscoveryDomain.md)


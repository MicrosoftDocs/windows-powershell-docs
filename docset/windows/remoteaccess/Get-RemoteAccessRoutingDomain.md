---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessRoutingDomain_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-RemoteAccessRoutingDomain
ms.reviewer:
ms.assetid: 35E46F63-030E-4C63-8398-5DCC6460043D
---

# Get-RemoteAccessRoutingDomain

## SYNOPSIS
Retrieves configuration information for a routing domain.

## SYNTAX

```
Get-RemoteAccessRoutingDomain [[-Name] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessRoutingDomain** cmdlet retrieves routing domain configuration for a multitenant system.

## EXAMPLES

### Example 1: Retrieve configuration for a specific routing domain
```
PS C:\> Get-RemoteAccessRoutingDomain -Name Rd_01

RoutingDomain                  : Rd_01
RoutingDomainID                : {11111111-1111-1111-1111-111111111001}
RoutingStatus                  : Enabled and Available
VpnStatus                      : Enabled   
VpnS2SStatus                   : Enabled
RoutingStatus                  : Enabled
EnableQoS                      : 
TxBandwidthKbps                : 1000000
RxBandwidthKbps                : 1000000
Capacity(Kbps)                 : 10240MaximumVpnConnections          : 
DnsIPAddress                   : 
NetBiosIPAddress               : 
TenantName                     : Contoso
IPAddressRange                 : {10.0.0.1 - 10.0.0.10}
IPv6Prefix                     : 3ffe:: 
IdleDisconnect(s)              : 0
SaADataSizeForRenegotiationDataSize(KB)    : 0
SALifeTime(s)                  : 0
InterimAccounting(s)           : 
EncryptionType                 : 
OptionalEncryption             :
```

This command retrieves configuration for a routing domain named Tenant01 in a multitenant environment

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the name of a routing domain.
If you do not specify this parameter, the cmdlet retrieves information for all routing domain configurations.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName, RoutingDomain

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnRoutingDomainConfig[]

## NOTES

## RELATED LINKS

[Disable-RemoteAccessRoutingDomain](./Disable-RemoteAccessRoutingDomain.md)

[Enable-RemoteAccessRoutingDomain](./Enable-RemoteAccessRoutingDomain.md)

[Set-RemoteAccessRoutingDomain](./Set-RemoteAccessRoutingDomain.md)


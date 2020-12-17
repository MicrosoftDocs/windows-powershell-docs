---
external help file: MSFT_DnsClient.cdxml-help.xml
Module Name: DnsClient
online version: 
schema: 2.0.0
title: Get-DnsClient
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: F89AA7EE-5BD8-4548-8672-7CA0852B32F9
---

# Get-DnsClient

## SYNOPSIS
Retrieves details of the network interfaces configured on a specified computer.

## SYNTAX

```
Get-DnsClient [-InterfaceIndex <UInt32[]>] [[-InterfaceAlias] <String[]>]
 [-ConnectionSpecificSuffix <String[]>] [-RegisterThisConnectionsAddress <Boolean[]>]
 [-UseSuffixWhenRegistering <Boolean[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsClient** cmdlet retrieves configuration details specific to the different network interfaces on a specified computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DnsClient
```

This example gets configuration details of network interfaces on a computer.

### EXAMPLE 2
```
PS C:\>$dnsClient1 = Get-DnsClient -InterfaceAlias "Wired Ethernet Connection"



PS C:\>Set-DnsClientServerAddress -InputObject $dnsClinet1 -ServerAddresses ("10.0.0.1","10.0.0.2")


This is a version of the cmdlet using the pipeline.
PS C:\>Get-DnsClient | Set-DnsClientServerAddress -ServerAddresses ("10.0.0.1","10.0.0.2")
```

This example sets the DNS server IP address on all of the wired Ethernet connections on a computer.

### EXAMPLE 3
```
PS C:\>Get-DnsClient | Set-DnsClientServerAddress -ResetServerAddresses
```

This example resets all of the network interfaces to use DHCP-specified DNS server addresses.

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

### -ConnectionSpecificSuffix
Specifies the connection-specific suffixes that are to be appended.
This parameter is a per-connection DNS suffix which will be appended to the computer name to construct a Fully Qualified Domain Name (FQDN).
This FQDN will be used as the host name for name resolution by the DNS client.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Suffix

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the friendly name of the interface.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the index number of the interface.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -RegisterThisConnectionsAddress
Specifies the registration policy for this interface. 

This parameter specifies that the computer should automatically register the IP address associated with this connection with the DNS server.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -UseSuffixWhenRegistering
Specifies the registration suffix policy for this interface. 

This parameter specifies that suffixes need to be used while registering an IP address.

```yaml
Type: Boolean[]
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClient
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClientServerAddress
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetAdapter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPInterface
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClient
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Register-DnsClient](./Register-DnsClient.md)

[Set-DnsClient](./Set-DnsClient.md)


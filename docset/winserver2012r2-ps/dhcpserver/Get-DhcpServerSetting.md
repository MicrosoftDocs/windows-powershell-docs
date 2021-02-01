---
external help file: PS_DhcpServerSetting_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Get-DhcpServerSetting
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: F0554EFC-7B52-46C2-933E-AFAF47B4FA6B
---

# Get-DhcpServerSetting

## SYNOPSIS
Gets the configuration parameters of the database of the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Get-DhcpServerSetting [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerSetting** cmdlet gets the configuration parameters of the database of the Dynamic Host Configuration Protocol (DHCP) server service.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerSetting -ComputerName dhcpserver.contoso.com
```

This example gets the DHCP server service settings for the DHCP server service on the computer named dhcpserver.contoso.com.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4DnsSetting](./Get-DhcpServerv4DnsSetting.md)

[Get-DhcpServerv6DnsSetting](./Get-DhcpServerv6DnsSetting.md)

[Set-DhcpServerSetting](./Set-DhcpServerSetting.md)

[Set-DhcpServerv4DnsSetting](./Set-DhcpServerv4DnsSetting.md)

[Set-DhcpServerv6DnsSetting](./Set-DhcpServerv6DnsSetting.md)


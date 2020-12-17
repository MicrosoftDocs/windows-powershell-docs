---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-HcsNetInterface
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8FA13E2E-7558-4491-8EB6-EF836384A2D0
---

# Enable-HcsNetInterface

## SYNOPSIS
Enables a network interface.

## SYNTAX

```
Enable-HcsNetInterface [-InterfaceAlias] <HcsNetInterfaces> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-HcsNetInterface** cmdlet enables a network interface.
If you previously enabled an interface and saved its settings, these settings stay in place if you disable and then enable the network interface.
These settings include the IP address.

## EXAMPLES

### Example 1: Enable a network interface
```
PS C:\> Enable-HcsNetInterface Data2


InterfaceAlias         : Data2
Controller0IPv4Address :
Controller0IPv6Address :
Controller1IPv4Address :
Controller1IPv6Address :
IPv4Address            :
IPv4Gateway            :
IPv4Netmask            :
IPv6Address            :
IPv6Gateway            :
IPv6Prefix             :
IsEnabled              : True
IsCloudEnabled         : False
IsiSCSIEnabled         : False
```

This command specifies the **InterfaceAlias** parameter to enable the Data2 network interface.

## PARAMETERS

### -InterfaceAlias
Specifies an interface alias.
The acceptable values for this parameter are:

- Data0
- Data1
- Data2
- Data3
- Data4
- Data5

```yaml
Type: HcsNetInterfaces
Parameter Sets: (All)
Aliases: 
Accepted values: Data0, Data1, Data2, Data3, Data4, Data5

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Platform.Support.NetInterfaceInfo
The NetInterfaceInfo object has the following properties:

- InterfaceAlias (Data0, Data1, Data2, Data3, Data4, or Data5) 
- IPAddress Controller0IPv4Address 
- IPAddress Controller 0 IPv6Address 
- IPAddress Controller 1 IPv4Address 
- IPAddress Controller 1 IPv6Address 
- IPAddress IPv4Address 
- IPAddress IPv4Gateway
- IPAddress IPv4Netmask 
- IPAddress IPv6Address 
- IPAddress IPv6Gateway 
- String IPv6Prefix 
- IsEnabled 
- IsCloudEnabled 
- IsiSCSIEnabled

## NOTES

## RELATED LINKS

[Disable-HcsNetInterface](./Disable-HcsNetInterface.md)

[Get-HcsNetInterface](./Get-HcsNetInterface.md)

[Set-HcsNetInterface](./Set-HcsNetInterface.md)


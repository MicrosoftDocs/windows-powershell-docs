---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/hcs/disable-hcsnetinterface?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-HcsNetInterface
---

# Disable-HcsNetInterface

## SYNOPSIS
Disables a network interface.

## SYNTAX

```
Disable-HcsNetInterface [-InterfaceAlias] <HcsDisableNetInterfaces> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-HcsNetInterface** cmdlet disables a network interface.
If you disable a network interface and then enable it, the IP address settings stay in place.

Note that you cannot disable the Data0 interface.

## EXAMPLES

### Example 1: Disable a network interface
```
PS C:\> Disable-HcsNetInterface Data2


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
IsEnabled              : False
IsCloudEnabled         : False
IsiSCSIEnabled         : False
```

This command specifies the **InterfaceAlias** parameter to disable the Data2 network interface.

## PARAMETERS

### -InterfaceAlias
Specifies an interface alias.
The acceptable values for this parameter are:

- Data1
- Data2 
- Data3
- Data4 
- Data5

```yaml
Type: HcsDisableNetInterfaces
Parameter Sets: (All)
Aliases: 
Accepted values: Data1, Data2, Data3, Data4, Data5

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

- HcsNetInterfaces InterfaceAlias (Data0, Data1, Data2, Data3, Data4, or Data5) 
- IPAddress Controller 0 IPv4Address 
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

[Get-HcsNetInterface](./Get-HcsNetInterface.md)

[Enable-HcsNetInterface](./Enable-HcsNetInterface.md)

[Set-HcsNetInterface](./Set-HcsNetInterface.md)


---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/hcs/get-hcsnetinterface?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HcsNetInterface
---

# Get-HcsNetInterface

## SYNOPSIS
Gets configuration information for a network interface.

## SYNTAX

```
Get-HcsNetInterface [[-InterfaceAlias] <HcsNetInterfaces>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsNetInterface** cmdlet gets configuration information for a network interface by specifying the **InterfaceAlias** parameter.

You can also use **Get-HcsNetInterface** with no parameter to get configuration information for all network interfaces on a device.

## EXAMPLES

### Example 1: Get network interface configuration information by alias
```
PS C:\> Get-HcsNetInterface Data0


InterfaceAlias         : Data0
Controller0IPv4Address : 10.126.172.231
Controller0IPv6Address : 
Controller1IPv4Address : 10.126.172.232
Controller1IPv6Address : 
IPv4Address            : 10.126.172.230
IPv4Gateway            : 10.126.172.1
IPv4Netmask            : 198.162.252.0
IPv6Address            : 
IPv6Gateway            : 
IPv6Prefix             : 
IsEnabled              : True
IsCloudEnabled         : True
IsiSCSIEnabled         : True
```

This command gets network interface configuration information for the network interface specified by the **InterfaceAlias** parameter.

### Example 2: Get network interface configuration information for all interfaces
```
PS C:\> Get-HcsNetInterface : 





InterfaceAlias         : Data0
Controller0IPv4Address : 10.126.172.231
Controller0IPv6Address :
Controller1IPv4Address : 10.126.172.232
Controller1IPv6Address :
IPv4Address            : 10.126.172.230
IPv4Gateway            : 10.126.172.1
IPv4Netmask            : 198.162.252.0
IPv6Address            :
IPv6Gateway            :
IPv6Prefix             :
IsEnabled              : True
IsCloudEnabled         : True
IsiSCSIEnabled         : True
[10.126.172.232]: Controller1>Get-HcsNetInterface


InterfaceAlias         : Data0
Controller0IPv4Address : 10.126.172.231
Controller0IPv6Address :
Controller1IPv4Address : 10.126.172.232
Controller1IPv6Address :
IPv4Address            : 10.126.172.230
IPv4Gateway            : 10.126.172.1
IPv4Netmask            : 198.162.252.0
IPv6Address            :
IPv6Gateway            :
IPv6Prefix             :
IsEnabled              : True
IsCloudEnabled         : True
IsiSCSIEnabled         : True

InterfaceAlias         : Data1
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

InterfaceAlias         : Data3
Controller0IPv4Address :
Controller0IPv6Address : 
Controller0IPv6Address : 
Controller1IPv4Address:
IPv4Address            :
IPv4Gateway            :
IPv4Netmask            :
IPv6Address            :
IPv6Gateway            :
IPv6Prefix             :
IsEnabled              : False
IsCloudEnabled         : False
IsiSCSIEnabled         : False

InterfaceAlias         : Data4
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

InterfaceAlias         : Data5
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

This command gets network configuration information for all network interfaces on a device.

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

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Platform.Support.NetInterfaceInfo[]
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

[Disable-HcsNetInterface](./Disable-HcsNetInterface.md)

[Enable-HcsNetInterface](./Enable-HcsNetInterface.md)

[Set-HcsNetInterface](./Set-HcsNetInterface.md)


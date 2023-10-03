---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/hcs/set-hcsnetinterface?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HcsNetInterface
---

# Set-HcsNetInterface

## SYNOPSIS
Sets the configuration for a single network interface by alias.

## SYNTAX

### Alias (Default)
```
Set-HcsNetInterface [-InterfaceAlias] <HcsNetInterfaces> [-Controller0IPv4Address <IPAddress>]
 [-Controller1IPv4Address <IPAddress>] [-IPv4Address <IPAddress>] [-IPv4Gateway <IPAddress>]
 [-IPv4Netmask <IPAddress>] [-IPv6Gateway <IPAddress>] [-IPv6Prefix <String>] [-IsCloudEnabled <Boolean>]
 [-IsiSCSIEnabled <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Clear
```
Set-HcsNetInterface [-InterfaceAlias] <HcsNetInterfaces> [-ClearIPv4] [-ClearIPv6] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-HcsNetInterface** cmdlet sets the configuration for a single network interface by alias.
Controller-specific addresses, such as Controller0IPv4Address, apply only to Data0.

## EXAMPLES

### Example 1: Set the IPv4 configuration for a network interface
```
PS C:\> Set-HcsNetInterface Data2 -IPv4Address 10.1.1.30 -IPv4Gateway 10.1.1.1 -IPv4Netmask 192.168.255.0
InterfaceAlias         : Data2
Controller0IPv4Address :
Controller0IPv6Address :
Controller1IPv4Address :
Controller1IPv6Address :
IPv4Address            : 10.1.1.30
IPv4Gateway            : 10.1.1.1
IPv4Netmask            : 192.168.255.0
IPv6Address            :
IPv6Gateway            :
IPv6Prefix             :
IsEnabled              : True
IsCloudEnabled         : False
IsiSCSIEnabled         : False
```

This command sets the IPv4 configuration for the network interface specified by the **InterfaceAlias** parameter.

### Example 2: Set the IPv6 gateway address
```
PS C:\> Set-HcsNetInterface Data2 -IPv6Prefix 2001:4898:4010:3015::/64 -IPv6Gateway 2001:4898:4010:3015::1


InterfaceAlias         : Data2
Controller0IPv4Address :
Controller0IPv6Address :
Controller1IPv4Address :
Controller1IPv6Address :
IPv4Address            : 10.1.1.30
IPv4Gateway            : 10.1.1.1
IPv4Netmask            : 192.168.255.0
IPv6Address            : 2001:4898:4010:3015:ff1a:afe8:bd14:5608
IPv6Gateway            : 2001:4898:4010:3015::1
IPv6Prefix             : 2001:4898:4010:3015::/64
IsEnabled              : True
IsCloudEnabled         : False
IsiSCSIEnabled         : False
```

This command sets the IPv6 gateway address for the network interface specified by the **InterfaceAlias** parameter.
The IP address is automatically generated based on the **IPv6Prefix** parameter.

### Example 3: Clear IPv6 settings for a network interface
```
PS C:\> Set-HcsNetInterface Data2 -ClearIPv6


InterfaceAlias         : Data2
Controller0IPv4Address :
Controller0IPv6Address :
Controller1IPv4Address :
Controller1IPv6Address :
IPv4Address            : 10.1.1.30
IPv4Gateway            : 10.1.1.1
IPv4Netmask            : 192.168.255.0
IPv6Address            :
IPv6Gateway            :
IPv6Prefix             :
IsEnabled              : True
IsCloudEnabled         : False
IsiSCSIEnabled         : False
```

This command removes IPv6 settings from the network interface specified by the **InterfaceAlias** parameter.

### Example 4: Enable cloud access for a network interface
```
PS C:\> Set-HcsNetInterface Data2 -IsCloudEnabled $True


InterfaceAlias         : Data2
Controller0IPv4Address :
Controller0IPv6Address :
Controller1IPv4Address :
Controller1IPv6Address :
IPv4Address            : 10.1.1.30
IPv4Gateway            : 10.1.1.1
IPv4Netmask            : 192.168.255.0
IPv6Address            :
IPv6Gateway            :
IPv6Prefix             :
IsEnabled              : True
IsCloudEnabled         : True
IsiSCSIEnabled         : False
```

This command enables cloud access for the network interface specified by the **InterfaceAlias** parameter.

### Example 5: Enable iSCSI access for a network interface
```
PS C:\> Set-HcsNetInterface Data2 -IsiSCSIEnabled $True


InterfaceAlias         : Data2
Controller0IPv4Address :
Controller0IPv6Address :
Controller1IPv4Address :
Controller1IPv6Address :
IPv4Address            : 10.1.1.30
IPv4Gateway            : 10.1.1.1
IPv4Netmask            : 192.168.255.0
IPv6Address            :
IPv6Gateway            :
IPv6Prefix             :
IsEnabled              : True
IsCloudEnabled         : True
IsiSCSIEnabled         : True
```

This command enables iSCSI access for the network interface specified by the **InterfaceAlias** parameter.

## PARAMETERS

### -ClearIPv4
Indicates that the cmdlet removes all IPv4 addresses from a network interface.
If the network interface is only configured for IPv4, this cmdlet also disables the interface.

```yaml
Type: SwitchParameter
Parameter Sets: Clear
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClearIPv6
Indicates that the cmdlet removes all IPv6 addresses from a network interface.
If the network interface is only configured for IPv6, this cmdlet also disables the interface.

```yaml
Type: SwitchParameter
Parameter Sets: Clear
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Controller0IPv4Address
Specifies an IP address to directly target controller0.
You can configure only the Data0 network interface with a fixed IP address for controller0.
The Controller0IPv4 setting is ignored on all interfaces other than Data0.

```yaml
Type: IPAddress
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Controller1IPv4Address
Specifies an IP address to directly target controller1.
You can configure only the Data0 network interface with a fixed IP address for controller1.
The Controller1IPv4 setting is ignored on all interfaces other than Data0.

```yaml
Type: IPAddress
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Address
Specifies an IPv4 address.

```yaml
Type: IPAddress
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4Gateway
Specifies an IPv4 default gateway.

```yaml
Type: IPAddress
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4Netmask
Specifies the IPv4 prefix length in bits.
This field also accepts subnet format (for example, 255.255.255.0)

```yaml
Type: IPAddress
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Gateway
Specifies an IPv6 default gateway.

```yaml
Type: IPAddress
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Prefix
Specifies an IPv6 prefix.
When you specify this parameter, the cmdlet automatically generates an IPv6 address based on the prefix, ensures it does not have an IP conflict on the network, and sets that IPv6 address.

```yaml
Type: String
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsCloudEnabled
Indicates whether cloud access is enabled on an interface.
If you enable cloud access, you can use an interface to send data to the cloud and communicate with the azure_1 StorSimple Manager Service.
Data0 must always be cloud-enabled.

```yaml
Type: Boolean
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsiSCSIEnabled
Indicates whether iSCSI access is enabled on an interface.

```yaml
Type: Boolean
Parameter Sets: Alias
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.HCS.Management.Platform.Support.NetInterfaceInfo
The NetInterfaceInfo object has the following properties:

 -- HcsNetInterfaces InterfaceAlias (Data0, Data1, Data2, Data3, Data4, or Data5) 
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

[Get-HcsNetInterface](./Get-HcsNetInterface.md)


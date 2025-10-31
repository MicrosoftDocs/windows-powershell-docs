---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmnetworkadapterfailoverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMNetworkAdapterFailoverConfiguration
---

# Set-VMNetworkAdapterFailoverConfiguration

## SYNOPSIS
Configures the IP address of a virtual network adapter to be used when a virtual machine fails over.

## SYNTAX

### VMName (Default)
```
Set-VMNetworkAdapterFailoverConfiguration [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String> [-VMNetworkAdapterName <String>] [-IPv4Address <String>]
 [-IPv6Address <String>] [-IPv4SubnetMask <String>] [-IPv6SubnetPrefixLength <Int32>]
 [-IPv4PreferredDNSServer <String>] [-IPv4AlternateDNSServer <String>] [-IPv6PreferredDNSServer <String>]
 [-IPv6AlternateDNSServer <String>] [-IPv4DefaultGateway <String>] [-IPv6DefaultGateway <String>]
 [-ClearFailoverIPv4Settings] [-ClearFailoverIPv6Settings] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Set-VMNetworkAdapterFailoverConfiguration [-VMNetworkAdapter] <VMNetworkAdapter> [-IPv4Address <String>]
 [-IPv6Address <String>] [-IPv4SubnetMask <String>] [-IPv6SubnetPrefixLength <Int32>]
 [-IPv4PreferredDNSServer <String>] [-IPv4AlternateDNSServer <String>] [-IPv6PreferredDNSServer <String>]
 [-IPv6AlternateDNSServer <String>] [-IPv4DefaultGateway <String>] [-IPv6DefaultGateway <String>]
 [-ClearFailoverIPv4Settings] [-ClearFailoverIPv6Settings] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Set-VMNetworkAdapterFailoverConfiguration [-VM] <VirtualMachine> [-VMNetworkAdapterName <String>]
 [-IPv4Address <String>] [-IPv6Address <String>] [-IPv4SubnetMask <String>] [-IPv6SubnetPrefixLength <Int32>]
 [-IPv4PreferredDNSServer <String>] [-IPv4AlternateDNSServer <String>] [-IPv6PreferredDNSServer <String>]
 [-IPv6AlternateDNSServer <String>] [-IPv4DefaultGateway <String>] [-IPv6DefaultGateway <String>]
 [-ClearFailoverIPv4Settings] [-ClearFailoverIPv6Settings] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMNetworkAdapterFailoverConfiguration** cmdlet sets the configuration of an IP address of a virtual network adapter  to be used when a virtual machine fails over.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMNetworkAdapter VM01 NetworkAdapter01 | Set-VMNetworkAdapterFailoverConfiguration -IPv4Address 10.100.1.100 -IPv4SubnetMask 255.255.255.0
```

This example configures a failover IPv4 address for virtual network adapter NetworkAdapter01 on virtual machine VM01.

### Example 2
```
PS C:\> Get-VMNetworkAdapter VM01 NetworkAdapter01 | Set-VMNetworkAdapterFailoverConfiguration -ClearFailoverIPv4Settings
```

This example clears the current failover IPv4 settings on virtual network adapter NetworkAdapter01 for virtual machine VM01.

### Example 3
```
PS C:\> Get-VMNetworkAdapter VM01 NetworkAdapter01 | Set-VMNetworkAdapterFailoverConfiguration -Ipv6Address aaaa:aaaa:aaaa:aaaa:aaaa:aaaa:aaa:aaaa -Ipv6SubnetPrefixLength 12
```

This example configures an IPv6 address and a prefix length of 12 for a virtual network adapter NetworkAdapter01 for virtual machine VM01.

### Example 4
```
PS C:\> Get-VMNetworkAdapter VM01 NetworkAdapter01 | Set-VMNetworkAdapterFailoverConfiguration -ClearFailoverIPv6Settings
```

This example clears the current failover IPv6 settings on a virtual network adapter NetworkAdapter01 for virtual machine VM01.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClearFailoverIPv4Settings
Clears the configured IPv4 failover settings.
The IPv4 address configured in the primary virtual machine (static or dynamic) will be used by the Replica virtual machine.

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

### -ClearFailoverIPv6Settings
Clears the configured IPv6 failover settings.
The IPv6 address configured in the primary virtual machine (static or dynamic) will be used by the Replica virtual machine.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which the IP address configuration of a virtual network adapter is to be set.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Address
Specifies the IPv4 address to set on the VMNetworkAdapter for use on failover of the virtual machine.
You must also specify the **IPv4SubnetMask** parameter when you specify this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4AlternateDNSServer
Specifies the IPv4 alternate DNS server to be set on the VMNetworkAdapter for use on failover of the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4DefaultGateway
Specifies the IPv4 default gateway to be set on VMNetworkAdapter for use on failover of the virtual machine..

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4PreferredDNSServer
Specifies the IPv4 preferred DNS server to be set on VMNetworkAdapter for use on failover of the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4SubnetMask
Specifies the IPv4 subnet mask to be set on VMNetworkAdapter for use on failover of the virtual machine.
You must specify the **IPv4Address** parameter when you specify this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Address
Specifies the IPv6 address to be set on VMNetworkAdapter for use on failover of the virtual machine.
You must specify the **IPv6SubnetPrefixLength** parameter when you specify this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6AlternateDNSServer
Specifies the IPv6 alternate DNS server to be set on VMNetworkAdapter for use on failover of the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6DefaultGateway
Specifies the IPv6 default gateway to be set on VMNetworkAdapter for use on failover of the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6PreferredDNSServer
Specifies the IPv6 preferred DNS server to be set on VMNetworkAdapter for use on failover of the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6SubnetPrefixLength
Specifies the IPv6 subnet prefix length to be set on VMNetworkAdapter for use on failover of the virtual machine.
You must specify the **IPv6Address** parameter when you specify this parameter.

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

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMNetworkAdapterFailoverConfiguration** object is to be passed through to the pipeline representing the IP address configuration to be set.

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

### -VM
Specifies the virtual machine for which you want to configure the IP address.

```yaml
Type: VirtualMachine
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the friendly name of the virtual machine for which you want to configure the IP address.

```yaml
Type: String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter for which you want to configure the IP address.

```yaml
Type: VMNetworkAdapter
Parameter Sets: ResourceObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual network adapter for which you want to set the IP address.

```yaml
Type: String
Parameter Sets: VMName, VMObject
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMNetworkAdapterFailoverConfiguration
If **-PassThru** is specified.

## NOTES

## RELATED LINKS


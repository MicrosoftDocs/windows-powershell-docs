---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetIPConfiguration-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netipconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIPConfiguration
---

# Get-NetIPConfiguration

## SYNOPSIS
Gets IP network configuration.

## SYNTAX

### Alias (Default)
```
Get-NetIPConfiguration [[-InterfaceAlias] <String>] [-AllCompartments] [-CompartmentId <Int32>] [-Detailed]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### Index
```
Get-NetIPConfiguration -InterfaceIndex <Int32> [-AllCompartments] [-CompartmentId <Int32>] [-Detailed]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### All
```
Get-NetIPConfiguration [-All] [-AllCompartments] [-CompartmentId <Int32>] [-Detailed]
 [-CimSession <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetIPConfiguration** cmdlet gets network configuration, including usable interfaces, IP addresses, and DNS servers.

If you do not specify any parameters, this cmdlet gets IP configuration properties for all non-virtual connected interfaces on a computer.

## EXAMPLES

### Example 1: Get the IP configuration
```
PS C:\>Get-NetIPConfiguration
```

This command gets IP configuration information.
When this cmdlet is run without parameters, it gets the IP configuration information for all of the non-virtual connected interfaces on the computer.

### Example 2: Get all IP configuration details
```
PS C:\>Get-NetIPConfiguration -All
```

This command gets the IP configuration information for all of the interfaces on the computer, including virtual interfaces, loopback interfaces, and disconnected interfaces.

### Example 3: Get the IP configuration information with a common parameter
```
PS C:\>Get-NetIPConfiguration -Verbose
```

This command gets IP configuration information.
By using the *Verbose* parameter, the networking cmdlets are shown to gather and format the information displayed in this cmdlet.

### Example 4: Get the IP configuration by interface index
```
PS C:\>Get-NetIPConfiguration -InterfaceIndex 12
```

This command gets the IP configuration information for the interface at the index 12.

### Example 5: Get the IP configuration from pipeline input
```
PS C:\>Get-NetIPConfiguration | Get-NetIPAddress
```

This command gets the IP address information, including the prefix length.

## PARAMETERS

### -InterfaceAlias
Specifies an alias of a network interface.
The cmdlet gets an IP configuration that matches the alias.

```yaml
Type: String
Parameter Sets: Alias
Aliases: ifAlias

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -InterfaceIndex
Specifies an index of a network interface.
The cmdlet gets an IP configuration that matches the index.

```yaml
Type: Int32
Parameter Sets: Index
Aliases: ifIndex

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -All
Indicates that the cmdlet retrieves the IP configuration properties for all of the interfaces on a computer, including virtual interfaces, loopback interfaces, and disconnected interfaces.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: IncludeAllInterfaces

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllCompartments
Indicates that the cmdlet gets the IP configuration properties for all of the compartments on a computer.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: IncludeAllCompartments

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompartmentId
Specifies an identifier for network compartment in the protocol stack.
By default, the cmdlet gets Net IP configuration in the default compartment.
If you specify a value for this parameter, the cmdlet gets any matching Net IP configuration in the compartment specified in this field.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Detailed
Indicates that the cmdlet retrieves additional interface and computer configuration information, including the computer name, link layer address, network profile, MTU length, and DHCP status.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases: PSComputerName, ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DNSClientServerAddress](../dnsclient/Get-DnsClientServerAddress.md)

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

[Get-NetIPAddress](./Get-NetIPAddress.md)

[Get-NetIPInterface](./Get-NetIPInterface.md)

[Get-NetRoute](./Get-NetRoute.md)


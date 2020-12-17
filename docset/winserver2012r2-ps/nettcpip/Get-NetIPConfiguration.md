---
external help file: NetIPConfiguration-help.xml
Module Name: NetTCPIP
online version: 
schema: 2.0.0
title: Get-NetIPConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 54C9B3A3-77CF-428B-8005-0A416A4AB277
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NetIPConfiguration

## SYNOPSIS
Gets IP network configuration.

## SYNTAX

### Alias (Default)
```powershell
Get-NetIPConfiguration [[-InterfaceAlias] <String>] [-Detailed] [-CimSession <CimSession>] [<CommonParameters>]
```

### Index
```powershell
Get-NetIPConfiguration -InterfaceIndex <Int32> [-Detailed] [-CimSession <CimSession>] [<CommonParameters>]
```

### All
```powershell
Get-NetIPConfiguration [-All] [-Detailed] [-CimSession <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetIPConfiguration** cmdlet gets network configuration, including usable interfaces, IP addresses and DNS servers.

If you do not specify any parameters, this cmdlet gets IP configuration properties for all non-virtual connected interfaces on a computer.

## EXAMPLES

### Example 1: Get the IP configuration
```powershell
PS C:\> Get-NetIPConfiguration
```

This command gets IP configuration information.
When this cmdlet is run without parameters, it gets the IP configuration information for all of the non-virtual connected interfaces on the computer.

### Example 2: Get all IP configuration details
```powershell
PS C:\> Get-NetIPConfiguration -All
```

This command gets the IP configuration information for all of the interfaces on the computer, including virtual interfaces, loopback interfaces, and disconnected interfaces.

### Example 3: Get the IP configuration information with a common parameter
```powershell
PS C:\> Get-NetIPConfiguration -Verbose
```

This command gets IP configuration information.
By using the **Verbose** parameter, the networking cmdlets are shown to gather and format the information displayed in this cmdlet.

### Example 4: Get the IP configuration by interface index
```powershell
PS C:\> Get-NetIPConfiguration -InterfaceIndex 12
```

This command gets the IP configuration information for the interface at the index 12.

### Example 5: Get the IP configuration from pipeline input
```powershell
PS C:\> Get-NetIPConfiguration | Get-NetIPAddress
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
Accept wildcard characters: False
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
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

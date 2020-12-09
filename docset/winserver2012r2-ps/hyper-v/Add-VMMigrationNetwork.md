---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Add-VMMigrationNetwork
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4CC447AE-DAB0-45AF-B3A1-44CD4D380560
---

# Add-VMMigrationNetwork

## SYNOPSIS
Adds a network for virtual machine migration on one or more virtual machine hosts.

## SYNTAX

```
Add-VMMigrationNetwork [-ComputerName <String[]>] [-Subnet] <String> [[-Priority] <UInt32>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMMigrationNetwork** cmdlet adds a network for virtual machine migration on one or more virtual machine hosts.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMMigrationNetwork 192.168.0.1
```

This example adds an IPv4 address as a live migration network on the local Hyper-V host.

### Example 2
```
PS C:\>Add-VMMigrationNetwork 192.168.10.0/24
```

This example adds an IPv4 address range as possible live migration networks on the local Hyper-V host by using a subnet mask.

### Example 3
```
PS C:\>Add-VMMigrationNetwork 2001:836c:6456:1c99::/32
```

This example adds an IPv6 address range as possible live migration networks on the local Hyper-V host by adding a subnet mask.

### Example 4
```
PS C:\>Add-VMMigrationNetwork 2001:836c:6456:1c99::/64 -Priority 8
```

This example adds an IPv6 address range as possible live migration networks on the local Hyper-V host by using a subnet mask and specifying the network as lower priority.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the network is to be added for virtual machine migration.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
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

### -Passthru
Specifies that an **Microsoft.HyperV.PowerShell.MigrationNetwork** object is to be passed through to the pipeline representing the network added for virtual machine migration.

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

### -Priority
Specifies the priority of the network to be added for virtual machine migration.
Multiple networks can have the same priority.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Specifies a string representing an IPv4 or IPv6 subnet mask which identifies the network to be added for virtual machine migration.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

###  
None by default; **Microsoft.HyperV.PowerShell.MigrationNetwork** if **-PassThru** is specified.

## NOTES

## RELATED LINKS


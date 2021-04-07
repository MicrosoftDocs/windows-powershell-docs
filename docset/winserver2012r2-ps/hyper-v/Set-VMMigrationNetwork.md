---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmmigrationnetwork?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMMigrationNetwork
---

# Set-VMMigrationNetwork

## SYNOPSIS
Sets the subnet, subnet mask, and/or priority of a migration network.

## SYNTAX

```
Set-VMMigrationNetwork [-ComputerName <String[]>] [-Subnet] <String> [[-NewSubnet] <String>]
 [-NewPriority <UInt32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMMigrationNetwork** cmdlet sets the subnet, subnet mask, and/or priority of a migration network.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMMigrationNetwork 192.168.10.1 192.168.10.3
```

This example changes an IPv4 address on a migration network.

### Example 2
```
PS C:\>Set-VMMigrationNetwork 192.168.10.* 192.168.10.3
```

This example changes the IPv4 address on a migration network selected using a wildcard.

### Example 3
```
PS C:\>Set-VMMigrationNetwork 2001:836c:6456:1c99::/64 -NewPriority 12
```

This example changes the priority of a migration network to 12.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which migration network properties are to be set.
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

### -NewPriority
Specifies the new priority of the virtual machine migration network.
Multiple networks can have the same priority.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewSubnet
Specifies a string representing the new subnet value to be set on the migration network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.MigrationNetwork** is to be passed through to the pipeline representing the migration network to be configured.

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

### -Subnet
Specifies a string representing an IPv4 or IPv6 subnet mask which identifies the migration network whose properties are to be set.
Wildcards are allowed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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


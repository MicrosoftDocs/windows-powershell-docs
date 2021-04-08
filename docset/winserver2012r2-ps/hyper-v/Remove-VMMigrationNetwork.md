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
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmmigrationnetwork?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMMigrationNetwork
---

# Remove-VMMigrationNetwork

## SYNOPSIS
Removes a network from use with migration.

## SYNTAX

```
Remove-VMMigrationNetwork [-Subnet] <String> [-ComputerName <String[]>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMMigrationNetwork** cmdlet removes a network from use with migration.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMMigrationNetwork 2001:836c:6456:1c99::/64
```

Remove an IPv6 network for use with migration.

### Example 2
```
PS C:\>Remove-VMMigrationNetwork 192.168.*
```

Remove all networks starting with 192.168 for use with migration.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the network is to be removed from use with migration.
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
Specifies that a **Microsoft.HyperV.PowerShell.MigrationNetwork** object is to be passed through to the pipeline representing the network removed from use with migration.

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
Specifies a string representing an IPv4 or IPv6 subnet mask which identifies the network to be removed from use with migration.

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


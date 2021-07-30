---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmmigrationnetwork?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMMigrationNetwork
---

# Get-VMMigrationNetwork

## SYNOPSIS
Gets the networks added for migration to one or more virtual machine hosts.

## SYNTAX

```
Get-VMMigrationNetwork [-ComputerName <String[]>] [[-Subnet] <String[]>] [-Priority <UInt32[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMMigrationNetwork** cmdlet gets the networks added for migration to one or more virtual machine hosts.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMMigrationNetwork
```

Gets all networks added for migration to the local virtual machine host.

### Example 2
```
PS C:\>Get-VMMigrationNetwork -Priority 8
```

Gets all networks added for migration to the local virtual machine host having a priority of 8.

### Example 3
```
PS C:\>Get-VMMigrationNetwork 192.168.*
```

Gets all networks added for migration having a subnet starting with 192.168.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the networks added for migration are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Priority
Specifies the priority of the networks to be retrieved.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Specifies a string representing an IPv4 or IPv6 subnet mask which identifies the networks to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.MigrationNetwork

## NOTES

## RELATED LINKS


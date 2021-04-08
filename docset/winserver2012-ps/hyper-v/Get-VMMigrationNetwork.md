---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmmigrationnetwork?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMMigrationNetwork

## SYNOPSIS
Gets the networks added for migration to one or more virtual machine hosts.

## SYNTAX

```
Get-VMMigrationNetwork [[-Subnet] <String[]>] [-ComputerName <String[]>] [-Priority <UInt32[]>]
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
Accept pipeline input: True (ByValue, ByPropertyName)
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.MigrationNetwork

## NOTES

## RELATED LINKS




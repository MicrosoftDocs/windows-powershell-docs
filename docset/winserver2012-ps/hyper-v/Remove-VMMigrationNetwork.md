---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmmigrationnetwork?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMMigrationNetwork

## SYNOPSIS
Removes a network from use with migration.

## SYNTAX

```
Remove-VMMigrationNetwork [-Subnet] <String> [-ComputerName <String[]>] [-Passthru] [-Confirm] [-WhatIf]
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

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.MigrationNetwork** object is to be passed through to the pipeline representing the network removed from use with migration.

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
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: True
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.MigrationNetwork
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




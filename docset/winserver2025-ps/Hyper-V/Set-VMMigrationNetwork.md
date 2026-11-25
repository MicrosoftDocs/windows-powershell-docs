---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmmigrationnetwork?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMMigrationNetwork
---

# Set-VMMigrationNetwork

## SYNOPSIS
Sets the subnet, subnet mask, and/or priority of a migration network.

## SYNTAX

### ComputerName (Default)
```
Set-VMMigrationNetwork [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-Subnet] <String>
 [[-NewSubnet] <String>] [-NewPriority <UInt32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimSession
```
Set-VMMigrationNetwork [-CimSession <CimSession[]>] [-Subnet] <String> [[-NewSubnet] <String>]
 [-NewPriority <UInt32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMMigrationNetwork** cmdlet sets the subnet, subnet mask, and/or priority of a migration network.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMMigrationNetwork 192.168.10.1 192.168.10.3
```

This example changes an IPv4 address on a migration network.

### Example 2
```
PS C:\> Set-VMMigrationNetwork 192.168.10.* 192.168.10.3
```

This example changes the IPv4 address on a migration network selected using a wildcard.

### Example 3
```
PS C:\> Set-VMMigrationNetwork 2001:836c:6456:1c99::/64 -NewPriority 12
```

This example changes the priority of a migration network to 12.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which this cmdlet operates.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: ComputerName
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
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.MigrationNetwork
If **-PassThru** is specified.

## NOTES

## RELATED LINKS


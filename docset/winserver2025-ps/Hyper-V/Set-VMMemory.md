---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmmemory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMMemory
---

# Set-VMMemory

## SYNOPSIS
Configures the memory of a virtual machine.

## SYNTAX

### VMName (Default)
```
Set-VMMemory [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-Buffer <Int32>] [-DynamicMemoryEnabled <Boolean>] [-MaximumBytes <Int64>]
 [-StartupBytes <Int64>] [-MinimumBytes <Int64>] [-Priority <Int32>] [-MaximumAmountPerNumaNodeBytes <Int64>]
 [-ResourcePoolName <String>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMMemory [-VM] <VirtualMachine[]> [-Buffer <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-MaximumBytes <Int64>] [-StartupBytes <Int64>] [-MinimumBytes <Int64>] [-Priority <Int32>]
 [-MaximumAmountPerNumaNodeBytes <Int64>] [-ResourcePoolName <String>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Set-VMMemory [-VMMemory] <VMMemory[]> [-Buffer <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-MaximumBytes <Int64>] [-StartupBytes <Int64>] [-MinimumBytes <Int64>] [-Priority <Int32>]
 [-MaximumAmountPerNumaNodeBytes <Int64>] [-ResourcePoolName <String>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMMemory** cmdlet configures the memory of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMMemory TestVM -DynamicMemoryEnabled $true -MinimumBytes 64MB -StartupBytes 256MB -MaximumBytes 2GB -Priority 80 -Buffer 25
```

Enables dynamic memory on virtual machine TestVM, sets its minimum, startup, and maximum memory, its memory priority, and its buffer.

## PARAMETERS

### -Buffer
Specifies the percentage of memory to reserve as a buffer in the virtual machine to be configured.
Allowed values range from 5 to 2000.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which the memory of a virtual machine is to be configured.
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

### -DynamicMemoryEnabled
Specifies whether dynamic memory is to be enabled on the virtual machine to be configured.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumAmountPerNumaNodeBytes
Specifies the maximum amount of memory per NUMA node in the virtual machine to be configured.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumBytes
Specifies the maximum amount of memory to be used by a virtual machine which has dynamic memory enabled.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumBytes
Specifies the minimum amount of memory to be used by a virtual machine which has dynamic memory enabled.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.Memory** object is to be passed through to the pipeline representing the virtual machine memory to be configured.

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
Sets the priority for memory availability to this virtual machine relative to other virtual machines on the virtual machine host.
Allowed values range from 0 to 100.

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

### -ResourcePoolName
Specifies the name of the memory resource pool for this virtual machine.

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

### -StartupBytes
Specifies the initial amount of memory to be assigned to a virtual machine with dynamic memory enabled, or the total amount of memory to be assigned to a virtual machine with dynamic memory disabled.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose memory is to be configured.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMemory
Specifies the virtual machine memory to be configured.

```yaml
Type: VMMemory[]
Parameter Sets: ResourceObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose memory is to be configured.

```yaml
Type: String[]
Parameter Sets: VMName
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.Memory
If **-PassThru** is specified.

## NOTES

## RELATED LINKS


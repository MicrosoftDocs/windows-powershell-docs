---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmgroupmember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMGroupMember
---

# Add-VMGroupMember

## SYNOPSIS
Adds group members to a virtual machine group.

## SYNTAX

### VM Using Name (Default)
```
Add-VMGroupMember [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String> [-VM] <VirtualMachine[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMGroup Using Name
```
Add-VMGroupMember [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String> [-VMGroupMember] <VMGroup[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VM Using ID
```
Add-VMGroupMember [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Id] <Guid> [-VM] <VirtualMachine[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMGroup Using ID
```
Add-VMGroupMember [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Id] <Guid> [-VMGroupMember] <VMGroup[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMGroup Using InputObject
```
Add-VMGroupMember [-VMGroup] <VMGroup> [-VMGroupMember] <VMGroup[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VM Using InputObject
```
Add-VMGroupMember [-VMGroup] <VMGroup> [-VM] <VirtualMachine[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMGroupMember** cmdlet adds members to a virtual machine group.
Groups can contain either virtual machines or groups of virtual machines.

## EXAMPLES

### Example 1: Add virtual machines to a group
```
PS C:\> $VM01 = Get-VM -Name "ContosoVirtualMachine01"
PS C:\> $VM02 = Get-VM -Name "ContosoVirtualMachine02"
PS C:\> Add-VMGroupMember -Name "VirtualMachineGroup" -VM $VM01, $VM02
```

The first two commands use the **Get-VM** cmdlet to get virtual machines named ContosoVirtualMachine01 and ContosoVirtualMachine02.
The commands store these virtual machine objects in the **$VM01** and **$VM02** variables.

The final command adds the virtual machines in **$VM01** and **$VM02** to the virtual machine group named VirtualMachineGroup.

### Example 2: Add groups to a group
```
PS C:\> $VMGroup01 = Get-VMGroup -Name "ContosoGroup01"
PS C:\> $VMGroup02 = Get-VMGroup -Name "ContosoGroup02"
PS C:\> Add-VMGroupMember -Name "ContosoMainGroup" -VMGroupMember $VMGroup01, $VMGroup02
```

The first two commands use the **Get-VMGroup** cmdlet to get virtual machine groups named ContosoGroup01 and ContosoGroup02.
The commands store these group objects in the **$VMGroup01** and **$VMGroup02** variables.

The final commad adds the groups in **$VMGroup01** and **$VMGroup02** to the group named ContosoMainGroup.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VM Using Name, VMGroup Using Name, VM Using ID, VMGroup Using ID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies on or more Hyper-V hosts where this cmdlet adds a group member.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VM Using Name, VMGroup Using Name, VM Using ID, VMGroup Using ID
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
Parameter Sets: VM Using Name, VMGroup Using Name, VM Using ID, VMGroup Using ID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the unique ID of the virtual machine group to which this cmdlet adds virtual machines or groups of virtual machines.

```yaml
Type: Guid
Parameter Sets: VM Using ID, VMGroup Using ID
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine group to which this cmdlet adds virtual machines or groups of virtual machines.

```yaml
Type: String
Parameter Sets: VM Using Name, VMGroup Using Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Indicates that this cmdlet returns the **Microsoft.HyperV.PowerShell.VMGroup** object that it configures.

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

### -VM
Specifies an array of virtual machines that this cmdlet adds to a virtual machine group.
To obtain a **VirtualMachine** object, use the **Get-VM** cmdlet.

```yaml
Type: VirtualMachine[]
Parameter Sets: VM Using Name, VM Using ID, VM Using InputObject
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMGroup
Specifies the virtual machine group to which this cmdlet adds virtual machines or groups of virtual machines.
To obtain a **VMGroup** object, use the **Get-VMGroup** cmdlet.

```yaml
Type: VMGroup
Parameter Sets: VMGroup Using InputObject, VM Using InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMGroupMember
Specifies an array of virtual machine groups that this cmdlet adds to a virtual machine group.

```yaml
Type: VMGroup[]
Parameter Sets: VMGroup Using Name, VMGroup Using ID, VMGroup Using InputObject
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

### Microsoft.HyperV.PowerShell.VMGroup
This cmdlet returns a **VMGroup** object, if you specify the **Passthru** parameter.

## NOTES

## RELATED LINKS

[Remove-VMGroupMember](./Remove-VMGroupMember.md)

[Get-VM](./Get-VM.md)

[Get-VMGroup](./Get-VMGroup.md)


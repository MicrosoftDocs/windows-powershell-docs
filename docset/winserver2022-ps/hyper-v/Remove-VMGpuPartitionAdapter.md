---
description: Removes an assigned GPU partition from a virtual machine.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 09/22/2022
online version: https://learn.microsoft.com/en-us/powershell/module/hyper-v/remove-vmgpupartitionadapter?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0

---

# Remove-VMGpuPartitionAdapter

## SYNOPSIS
Removes an assigned GPU partition from a virtual machine.

## SYNTAX

### VMName (Default)
```
Remove-VMGpuPartitionAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-Passthru] [-AdapterId <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Remove-VMGpuPartitionAdapter [-VM] <VirtualMachine[]> [-Passthru] [-AdapterId <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Object
```
Remove-VMGpuPartitionAdapter [-VMGpuPartitionAdapter] <VMGpuPartitionAdapter[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The 'Remove-VMGpuPartitionAdapter' cmdlet removes an assigned graphic processing unit partition from a virtual machine and releases that partition back to the host GPU.

## EXAMPLES

### Example 1
```powershell
$testvm = Get-VM "TestVM"
Remove-VMGpuPartitionAdapter -VM $testvm
```

Removes a partition assigned to a specific VM Object.

### Example 2
```powershell
$testvm = Get-VM "TestVM"
$GPUpartition = Get-VMGpuPartitionAdapter -VM $testvm
Remove-VMGpuPartitionAdapter -VM $testvm -AdapterId $GPUpartiton[0].id
```

Remove a specific partition in a VM

## PARAMETERS

### -AdapterId
A VM's GPU partition identification number used to remove a GPU from a VM.

```yaml
Type: String
Parameter Sets: VMName, VMObject
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
Specifies that one or more Hyper-V hosts on the virtual network adapters are to be retrieved. NetBIOS names, IP addresses, and fully qualified domain names are allowed.
The default is the local computer.Use localhost or a dot ('.') to specify the local computer explicitly.

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

### -Passthru
Returns an object for each process that the cmdlet started.

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
Specifies the virtual machine whose virtual network adapters are to be retrieved. The asterisk, ('*'), is the wildcard.
If it is specified the cmdlet returns virtual network adapters from every virtual machine in the system.

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

### -VMGpuPartitionAdapter
GPU partition object obtained from 'Get-VMGpuPartitionAdapter'.

```yaml
Type: VMGpuPartitionAdapter[]
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose network adapters are to be retrieved.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine[]

### Microsoft.HyperV.PowerShell.VMGpuPartitionAdapter[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMGpuPartitionAdapter

## NOTES

## RELATED LINKS

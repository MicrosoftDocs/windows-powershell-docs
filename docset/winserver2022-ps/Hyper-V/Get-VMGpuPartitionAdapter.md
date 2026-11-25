---
description: Gets the information of assigned GPU partitions to a virtual machine.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmgpupartitionadapter?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMGpuPartitionAdapter
---

# Get-VMGpuPartitionAdapter

## SYNOPSIS
Gets the information of assigned GPU partitions to a virtual machine.

## SYNTAX

### VMName (Default)

```
Get-VMGpuPartitionAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-AdapterId <String>] [<CommonParameters>]
```

### VMObject

```
Get-VMGpuPartitionAdapter [-VM] <VirtualMachine[]> [-AdapterId <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-VMGpuPartitionAdapter` cmdlet gets the information of assigned graphic processing unit
partitions to a virtual machine.

## EXAMPLES

### Example 1

```powershell
$testvm = Get-VM "TestVM"
Get-VMGpuPartitionAdapter -VM $testvm
```

This example gets the GPU information assigned to a VM object.

## PARAMETERS

### -AdapterId

This is a VM's GPU partition identification number used to display the GPU information assigned to a
VM.

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

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

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

Specifies one or more Hyper-V hosts on the virtual network adapters are to be retrieved. NetBIOS
names, IP addresses, and fully qualified domain names are allowed. The default is the local
computer. Use localhost or a dot (`.`) to specify the local computer explicitly.

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

Specifies one or more user accounts that have permission to perform this action. The default is the
current user.

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

### -VM

Specifies the virtual machine whose virtual network adapters are to be retrieved. The asterisk (`*`)
is the wildcard. If it is specified the cmdlet returns virtual network adapters from every virtual
machine in the system.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
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
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String[]

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMGpuPartitionAdapter

## NOTES

## RELATED LINKS

[Add-VMGpuPartitionAdapter](add-vmgpupartitionadapter.md)

[Remove-VMGpuPartitionAdapter](remove-vmgpupartitionadapter.md)

[Set-VMGpuPartitionAdapter](set-vmgpupartitionadapter.md)

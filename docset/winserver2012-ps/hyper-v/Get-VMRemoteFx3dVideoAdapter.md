---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmremotefx3dvideoadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMRemoteFx3dVideoAdapter

## SYNOPSIS
Gets the RemoteFX video adapter of a virtual machine or snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMRemoteFx3dVideoAdapter [-VMName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMRemoteFx3dVideoAdapter [-VM] <VirtualMachine[]>
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMRemoteFx3dVideoAdapter [-VMSnapshot] <VMSnapshot>
```

## DESCRIPTION
The **Get-VMRemoteFx3dVideoAdapter** cmdlet gets the RemoteFX video adapter of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMRemoteFx3dVideoAdapter -VMName TestVM
```

Gets the RemoteFX adapter from virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name TestVM | Get-VMRemoteFx3dVideoAdapter
```

Gets the RemoteFx adapter from virtual machine TestVM.

### Example 3
```
PS C:\>Get-VMSnapshot -VMName TestVM -Name 'Before applying updates' | Get-VMRemoteFx3dVideoAdapter
```

Gets the RemoteFx adapter from snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the RemoteFX video adapter is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose RemoteFX video adapter is to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose RemoteFX video adapter is to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -VMSnapshot
Specifies the snapshot whose RemoteFX video adapter is to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.RemoteFxVideoAdapter

## NOTES

## RELATED LINKS




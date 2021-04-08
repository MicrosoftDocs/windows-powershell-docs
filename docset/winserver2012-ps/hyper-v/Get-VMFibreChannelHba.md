---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmfibrechannelhba?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMFibreChannelHba

## SYNOPSIS
Gets the Fibre Channel host bus adapters associated with one or more virtual machines.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMFibreChannelHba [-VMName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMFibreChannelHba [-VM] <VirtualMachine[]>
```

## DESCRIPTION

## EXAMPLES

### Example 1
```
PS C:\>Get-VMFibreChannelHba -VMName MyVM
```

Gets the Fibre Channel host bus adapters associated with the virtual machine MyVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the Fibre Channel host bus adapters are to be retrieved.
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
Specifies a virtual machine or machines for which the Fibre Channel host bus adapters are to be retrieved.

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
Specifies the friendly name or names of the virtual machines for which the Fibre Channel host bus adapters are to be retrieved.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS




---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-VMNetworkAdapter

## SYNOPSIS
Removes one or more virtual network adapters from a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMNetworkAdapter [-VMName] <String[]> [-ComputerName <String[]>] [-Name <String>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMNetworkAdapter [-ComputerName <String[]>] [-Name <String>] [-Passthru] [-SwitchName <String>]
 [-VMNetworkAdapterName <String>] [-ManagementOS] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-VMNetworkAdapter [-VM] <VirtualMachine[]> [-Name <String>] [-Passthru] [-VMNetworkAdapterName <String>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Remove-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-Passthru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VMNetworkAdapter** cmdlet removes one or more virtual network adapters from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMNetworkAdapter -VMName Redmond -VMNetworkAdapterName Redmond_NIC1
```

This example removes network adapter Redmond_NIC1 from a virtual machine named Redmond.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual network adapter is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies the management operating system  of the virtual network adapter to be removed.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object to be passed through to the pipeline representing the virtual machine network adapter to be removed.
This is a **Microsoft.Virtualization.Powershell.VMInternalNetworkAdapter** object, if **-ManagementOS** is specified; otherwise it is a **Microsoft.Virtualization.Powershell.VMNetworkAdapter** object.

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
Specifies the virtual machine that has the virtual network adapter you want to remove.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine that has the virtual network adapter you want to remove.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual machine network adapter to be removed.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual network adapter to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual network adapter to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: VMNetworkAdapterName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchName
Specifies the name of the virtual switch connected to the virtual network adapter to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

### 
None by default.
If **-PassThru** is specified, **Microsoft.Virtualization.Powershell.VMInternalNetworkAdapter**, if **-ManagementOS** is also specified;otherwise **Microsoft.Virtualization.Powershell.VMNetworkAdapter**.

## NOTES

## RELATED LINKS




---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/rename-vmnetworkadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-VMNetworkAdapter

## SYNOPSIS
Renames a virtual network adapter on a virtual machine or on the management operating system.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-VMNetworkAdapter [-VMName] <String[]> [-NewName] <String> [-ComputerName <String[]>] [-Name <String>]
 [-Passthru] [-VMNetworkAdapterName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-VMNetworkAdapter [-NewName] <String> [-ComputerName <String[]>] [-Name <String>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-ManagementOS] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Rename-VMNetworkAdapter [-VM] <VirtualMachine[]> [-NewName] <String> [-Name <String>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Rename-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-NewName] <String> [-Passthru] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Rename-VMNetworkAdapter** cmdlet renames a virtual network adapter on a virtual machine or on the management operating system.

## EXAMPLES

### Example 1
```
PS C:\>Rename-VMNetworkAdapter -VMName Redmond -NewName CoreNet
```

This example renames all the virtual network adapters of virtual machine Redmond to CoreNet.

### Example 1
```
PS C:\>Rename-VMNetworkAdapter -VMName Kirkland -Name Private -NewName CoreNet
```

This example renames the virtual network adapter Private to CoreNet in virtual machine Kirkland.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual network adapter is to be renamed.
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
Specifies that you want to rename a virtual network adapter that belongs to the management operating system.

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

### -Name
Specifies the existing name of the virtual network adapter.

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

### -NewName
Specifies the new name for the virtual network adapter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual network adapter to be renamed.
This is a **Microsoft.Virtualization.Powershell.VMInternalNetworkAdapter** object, if ManagementOS is specified; otherwise it is a **Microsoft.Virtualization.PowerShell.VMNetworkAdapter** object.

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
Specifies the virtual machine that has the virtual network adapter you want to rename.

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
Specifies the name of the virtual machine that has the virtual network adapter you want to rename.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter to be renamed.

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
Specifies the existing name of the virtual network adapter you want to rename.

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
If **-PassThru** is specified, then a **Microsoft.Virtualization.Powershell.VMInternalNetworkAdapter** object is passed through to the pipeline if **-ManagementOS** is also specified; otherwise a **Microsoft.Virtualization.PowerShell.VMNetworkAdapter** is passed.

## NOTES

## RELATED LINKS




---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmnetworkadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VMNetworkAdapter

## SYNOPSIS
Adds a virtual network adapter to a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMNetworkAdapter [-VMName] <String[]> [-ComputerName <String[]>] [-DynamicMacAddress] [-IsLegacy <Boolean>]
 [-Name <String>] [-Passthru] [-ResourcePoolName <String>] [-StaticMacAddress <String>] [-SwitchName <String>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMNetworkAdapter [-ComputerName <String[]>] [-DynamicMacAddress] [-ManagementOS] [-Name <String>]
 [-Passthru] [-StaticMacAddress <String>] [-SwitchName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-VMNetworkAdapter [-VM] <VirtualMachine[]> [-DynamicMacAddress] [-IsLegacy <Boolean>] [-Name <String>]
 [-Passthru] [-ResourcePoolName <String>] [-StaticMacAddress <String>] [-SwitchName <String>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Add-VMNetworkAdapter** cmdlet adds a virtual network adapter to a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMNetworkAdapter -VMName Redmond -Name "Redmond NIC1"
```

This example adds a virtual network adapter named Redmond NIC1 to a virtual machine named Redmond.

### Example 2
```
PS C:\>Add-VMNetworkAdapter -VMName Test -SwitchName Network
```

This example adds a virtual network adapter to a virtual machine named Test and connects it to a virtual switch named Network.

### Example 3
```
PS C:\>Get-VM Test | Add-VMNetworkAdapter -IsLegacy $true -Name Bootable
```

This example uses two cmdlets and the pipeline in one command to perform the operation.

### Example 4
```
PS C:\>Add-VMNetworkAdapter -ManagementOS -Name Secondary
```

This example adds a second virtual network adapter in the management operating system.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual network adapter is to be added.
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

### -DynamicMacAddress
Assigns a dynamically generated MAC address to the new virtual network adapter.

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

### -IsLegacy
Specifies whether the virtual network adapter is the legacy type.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: FALSE
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies the management operating system.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the new virtual network adapter.
The default value is "Network Adapter."

```yaml
Type: String
Parameter Sets: (All)
Aliases: VMNetworkAdapterName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to be pipeline representing the network adapter to be added.
If you specify **-ManagementOS**, the object passed is a **Microsoft.Virtualization.Powershell.VMInternalNetworkAdapter**; otherwise the object passed is a **Microsoft.Virtualization.Powershell.VMNetworkAdapter**.

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

### -ResourcePoolName
Specifies the friendly name of a resource pool.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticMacAddress
Assigns a specific MAC address to the new virtual network adapter.

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

### -SwitchName
Specifies the name of the virtual switch to connect to the new network adapter.
If the switch name is not unique, then the operation fails.

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

### -VM
Specifies the virtual machine on which the network adapter is to be added.

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
Specifies the name of the virtual machine on which the network adapter is to be added.

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

### None

## OUTPUTS

### 
None by default; if **PassThru** is specified, then either a **Microsoft.Virtualization.Powershell.VMInternalNetworkAdapter** if **ManagementOS** is specified, or a **Microsoft.Virtualization.Powershell.VMNetworkAdapter** if it is not.

## NOTES

## RELATED LINKS




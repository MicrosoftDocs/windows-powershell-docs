---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmswitchextensionportfeature?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMSwitchExtensionPortFeature

## SYNOPSIS
Removes a feature from a virtual network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMSwitchExtensionPortFeature [-VMName] <String[]> [-ComputerName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMSwitchExtensionPortFeature [-SwitchName] <String> [-ComputerName <String[]>] [-Passthru]
 [-ExternalPort] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-VMSwitchExtensionPortFeature [-ComputerName <String[]>] [-Passthru] [-VMNetworkAdapterName <String>]
 [-ManagementOS] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Remove-VMSwitchExtensionPortFeature [-VM] <VirtualMachine[]> [-Passthru] [-VMNetworkAdapterName <String>]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Remove-VMSwitchExtensionPortFeature [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VMSwitchExtensionPortFeature** removes a feature from a virtual network adapter.
The feature must have already been configured on the virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\>$feature = Get-VMSwitchExtensionPortFeature -VMName VM2 -FeatureId 776e0ba7-94a1-41c8-8f28-951f524251b5
PS C:\>Remove-VMSwitchExtensionPortFeature VM2 -VMSwitchExtensionFeature $feature
```

Removes a feature configured on the virtual network adapter(s) on a virtual machine.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the feature is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPort
Specifies the external port on the virtual switch that binds to a physical network adapter.

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

### -ManagementOS
Specifies that the feature is to be removed from the management (e.g.
the parent, or host) operating system.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionPortFeature** is to be passed through to the pipeline representing the feature to be removed.

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

### -SwitchName
Specifies the name of the virtual switch from which the feature is to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine from which the feature is to be removed.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the feature is to be removed.

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
Specifies the virtual machine network adapter from which the feature is to be removed.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual network adapter from which the feature is to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitchExtensionFeature
Specifies the feature to be removed.

```yaml
Type: VMSwitchExtensionPortFeature[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMSwitchExtensionPortFeature
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




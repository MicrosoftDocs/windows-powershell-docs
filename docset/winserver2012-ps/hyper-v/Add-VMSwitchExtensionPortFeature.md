---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmswitchextensionportfeature?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VMSwitchExtensionPortFeature

## SYNOPSIS
Adds a feature to a virtual network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMSwitchExtensionPortFeature [-VMName] <String[]> [-ComputerName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMSwitchExtensionPortFeature [-SwitchName] <String> [-ComputerName <String[]>] [-Passthru] [-ExternalPort]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-VMSwitchExtensionPortFeature [-ComputerName <String[]>] [-Passthru] [-VMNetworkAdapterName <String>]
 [-ManagementOS] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-VMSwitchExtensionPortFeature [-VM] <VirtualMachine[]> [-Passthru] [-VMNetworkAdapterName <String>]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Add-VMSwitchExtensionPortFeature [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-VMSwitchExtensionPortFeature** cmdlet adds a feature supported by a virtual switch extension to a virtual machine network adapter.
This cmdlet also configures built-in virtual switch features.

## EXAMPLES

### Example 1
```
PS C:\>$feature = Get-VMSystemSwitchExtensionPortFeature -FeatureName "Ethernet Switch Port Security Settings"
PS C:\>$feature.SettingData.EnableDhcpGuard = $true
PS C:\>$feature.SettingData.EnableRouterGuard = $true
PS C:\>Add-VMSwitchExtensionPortFeature -VMName VM2 -VMSwitchExtensionFeature $feature
```

Adds a feature to virtual machine VM2.
The feature here is a port security feature supported by the extension Microsoft Virtual Ethernet Switch Native Extension.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a feature is to be added to a virtual network adapter.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPort
Specifies the virtual switch port connected to the external network interface card.

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
Specifies that the feature is to be added in the management (i.e.
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
Specifies that an object is to be passed through to the pipeline representing the feature to be added.

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
Specifies the name of the virtual switch.

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
Specifies the virtual machine in which the feature is to be added.

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
Specifies the name of the virtual machine in which the feature is to be added.

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
Specifies the virtual machine network adapter for which the feature is to be added.

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
Specifies the name of the virtual machine network adapter for which the feature is to be added.

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
Specifies the feature to be added to the virtual switch.
You can get such a feature object from Get-VMSystemSwitchExtensionPortFeature to add a new configuration to a virtual network adapter, or from the Get-VMSwitchExtensionPortFeature cmdlet to update an existing configuration.

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




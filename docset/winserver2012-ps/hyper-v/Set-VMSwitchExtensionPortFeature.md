---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmswitchextensionportfeature?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMSwitchExtensionPortFeature

## SYNOPSIS
Configures a feature on a virtual network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMSwitchExtensionPortFeature [-VMName] <String[]> [-ComputerName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMSwitchExtensionPortFeature [-SwitchName] <String> [-ComputerName <String[]>] [-Passthru] [-ExternalPort]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMSwitchExtensionPortFeature [-ComputerName <String[]>] [-Passthru] [-VMNetworkAdapterName <String>]
 [-ManagementOS] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Set-VMSwitchExtensionPortFeature [-VM] <VirtualMachine[]> [-Passthru] [-VMNetworkAdapterName <String>]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Set-VMSwitchExtensionPortFeature [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VMSwitchExtensionPortFeature** cmdlet configures a feature on a virtual network adapter.
The feature must have been configured previously on the virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\>$ModifiedFeature = Get-VMSwitchExtensionPortFeature -VMName VM2 -FeatureName "Ethernet Switch Port Security Settings"
PS C:\>$ModifiedFeature.SettingData.EnableDhcpGuard = $false
PS C:\>Set-VMSwitchExtensionPortFeature -VMName VM2 -VMSwitchExtensionFeature $ModifiedFeature
```

Configures the feature on a virtual network adapter(s) on virtual machine VM2.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a feature on a virtual network adapter is to be configured.
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
Specifies the management (e.g.
parent, or host) operating system.

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
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionPortFeature** object is to be passed through to the pipeline representing the feature to be configured.

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
Specifies the virtual machine on which the feature is to be configured.

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
Specifies the name of the virtual machine on which the feature is to be configured.

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
Specifies the virtual network adapter.

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
Specifies the name of the virtual network adapter.

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
Specifies the feature to be configured.

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




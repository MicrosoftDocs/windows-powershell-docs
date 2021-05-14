---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmswitchextensionportfeature?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMSwitchExtensionPortFeature

## SYNOPSIS
Gets the features configured on a virtual network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMSwitchExtensionPortFeature [-VMName] <String[]> [-ComputerName <String[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>]
 [-Passthru] [-VMNetworkAdapterName <String>] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMSwitchExtensionPortFeature [-SwitchName] <String> [-ComputerName <String[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>]
 [-Passthru] [-ExternalPort] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMSwitchExtensionPortFeature [-ComputerName <String[]>] [-Extension <VMSwitchExtension[]>]
 [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-ManagementOS] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
```

### UNNAMED_PARAMETER_SET_4
```
Get-VMSwitchExtensionPortFeature [-VM] <VirtualMachine[]> [-Extension <VMSwitchExtension[]>]
 [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
```

### UNNAMED_PARAMETER_SET_5
```
Get-VMSwitchExtensionPortFeature [-VMNetworkAdapter] <VMNetworkAdapterBase[]>
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>]
 [-Passthru] -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
```

## DESCRIPTION
The **Get-VMSwitchExtensionPortFeature** cmdlet gets the features configured on a virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSwitchExtensionPortFeature -VMName VM2 -FeatureName "Ethernet Switch Port Security Settings"
```

Gets the feature configured on virtual machine VM2 by name Ethernet Switch Port Security Settings.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts on which the features configured on a virtual network adapter are to be retrieved.
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

### -Extension
Specifies the virtual switch extension.

```yaml
Type: VMSwitchExtension[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionName
Specifies the name of the virtual switch extension.

```yaml
Type: String[]
Parameter Sets: (All)
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

### -FeatureId
Specifies the unique identifier of the feature supported by the virtual switch extension.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FeatureName
Specifies the name of the feature supported by the virtual switch extension.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that the features are to be retrieved from the management (i.e.
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
Specifies that an object is to be passed through to the pipeline representing the features configured on a virtual switch.

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
Specifies the virtual machine on which the features configured on a virtual switch are to be retrieved.

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
Specifies the name of the virtual machine on which the features configured on a virtual switch are to be retrieved.

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
Specifies the network adapter.

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
Specifies the name of the network adapter.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS




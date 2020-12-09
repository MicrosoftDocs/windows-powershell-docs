---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-VMSwitchExtensionPortData

## SYNOPSIS
Retrieves the status of a virtual switch extension feature applied to a virtual network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMSwitchExtensionPortData [-VMName] <String[]> [-ComputerName <String[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>]
 [-Passthru] [-VMNetworkAdapterName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMSwitchExtensionPortData [-SwitchName] <String> [-ComputerName <String[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>]
 [-Passthru] [-ExternalPort]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMSwitchExtensionPortData [-ComputerName <String[]>] [-Extension <VMSwitchExtension[]>]
 [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-ManagementOS]
```

### UNNAMED_PARAMETER_SET_4
```
Get-VMSwitchExtensionPortData [-VM] <VirtualMachine[]> [-Extension <VMSwitchExtension[]>]
 [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-VMSwitchExtensionPortData [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-Extension <VMSwitchExtension[]>]
 [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-Passthru]
```

## DESCRIPTION
The **Get-VMSwitchExtensionPortData** cmdlet retrieves the status of a virtual switch extension feature applied to a virtual network adapter.
This port feature data surfaces runtime information and statistics on a per-port basis.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSwitchExtensionPortData VM1 -FeatureId eb29f0f2-f5dc-45c6-81bb-3cd9f219bbbb
```

Gets the port feature data with ID eb29f0f2-f5dc-45c6-81bb-3cd9f219bbbb from the sample forwarding extension on the virtual network adapter in virtual machine VM1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the status of a virtual switch extension applied to a virtual network adapter is to be retrieved.
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
Specifies the virtual switch extension for which status is to be retrieved.

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
Specifies the name of the virtual switch extension for which status is to be retrieved.

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
Specifies that the status is to be retrieved from the management (i.e.
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
Specifies that an object is to be passed through to the pipeline representing the status to be retrieved.

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
Specifies the name of the virtual machine.

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
Specifies the virtual machine network adapter.

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
Specifies the name of the virtual machine network adapter.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS




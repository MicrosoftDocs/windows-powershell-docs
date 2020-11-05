---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-VMFibreChannelHba

## SYNOPSIS
Configures a Fibre Channel host bus adapter on a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMFibreChannelHba [-VMName] <String> [-WorldWideNodeNameSetA] <String> [-WorldWidePortNameSetA] <String>
 [-WorldWideNodeNameSetB] <String> [-WorldWidePortNameSetB] <String> [-ComputerName <String[]>] [-Passthru]
 -SanName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMFibreChannelHba [-VMName] <String> [-WorldWideNodeNameSetA] <String> [-WorldWidePortNameSetA] <String>
 [-WorldWideNodeNameSetB] <String> [-WorldWidePortNameSetB] <String> [-ComputerName <String[]>] [-Passthru]
 [-GenerateWwn] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMFibreChannelHba [-VMName] <String> [-WorldWideNodeNameSetA] <String> [-WorldWidePortNameSetA] <String>
 [-WorldWideNodeNameSetB] <String> [-WorldWidePortNameSetB] <String> [-ComputerName <String[]>]
 [-NewWorldWideNodeNameSetA <String>] [-NewWorldWideNodeNameSetB <String>] [-NewWorldWidePortNameSetA <String>]
 [-NewWorldWidePortNameSetB <String>] [-Passthru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Set-VMFibreChannelHba [-VMFibreChannelHba] <VMFibreChannelHba> [-Passthru] [-GenerateWwn] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Set-VMFibreChannelHba [-VMFibreChannelHba] <VMFibreChannelHba> [-NewWorldWideNodeNameSetA <String>]
 [-NewWorldWideNodeNameSetB <String>] [-NewWorldWidePortNameSetA <String>] [-NewWorldWidePortNameSetB <String>]
 [-Passthru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Set-VMFibreChannelHba [-VMFibreChannelHba] <VMFibreChannelHba> [-Passthru] -SanName <String> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-VMFibreChannelHba** cmdlet configures a Fibre Channel host bus adapter on a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMFibreChannelHba -VMName MyVM | Set-VMFibreChannelHba -GenerateWwn
```

Configures a Fibre Channel host bus adapter on a virtual machine named MyVM, with World Wide Names to be generated automatically.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a Fibre Channel host bus adapter is to be configured.
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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the configured Fibre Channel host bus adapter.

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

### -SanName
Specifies the name of the virtual storage area network (SAN) to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMFibreChannelHba
Specifies the Fibre Channel host bus adapter to be configured.

```yaml
Type: VMFibreChannelHba
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorldWideNodeNameSetA
Specifies the World Wide Node name of address set A that is associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: Wwnn1

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWideNodeNameSetB
Specifies the World Wide Node name of address set B that is associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: Wwnn2

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetA
Specifies the World Wide Port name of address set A that is associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: Wwpn1

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetB
Specifies the World Wide Port name of address set B that is associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: Wwpn2

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerateWwn
Specifies that the World Wide Names for sets A and B are to be generated automatically.
When this parameter is specified, parameters **WorldWideNodeNameSetA**, **WorldWideNodeNameSetB**, **WorldWidePortNameSetA**, and **WorldWidePortNameSetB** cannot be used.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWorldWideNodeNameSetA
Specifies the World Wide Node name of address set A to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWorldWideNodeNameSetB
Specifies the World Wide Node name of address set B to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWorldWidePortNameSetA
Specifies the World Wide Port name of address set A to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWorldWidePortNameSetB
Specifies the World Wide Port name of address set B to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine to which the virtual Fibre Channel host bus adapter parameters are to be set.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
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

## NOTES

## RELATED LINKS




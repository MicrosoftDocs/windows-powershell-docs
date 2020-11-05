---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-VMFibreChannelHba

## SYNOPSIS
Removes a Fibre Channel host bus adapter from a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMFibreChannelHba [-VMFibreChannelHba] <VMFibreChannelHba[]> [-ComputerName <String[]>] [-Passthru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMFibreChannelHba [-VMName] <String> [-WorldWideNodeNameSetA] <String> [-WorldWidePortNameSetA] <String>
 [-WorldWideNodeNameSetB] <String> [-WorldWidePortNameSetB] <String> [-ComputerName <String[]>] [-Passthru]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VMFibreChannelHba** removes a Fibre Channel host bus adapter from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMFibreChannelHba -VMName MyVM | Remove-VMFibreChannelHba
```

Removes a Fibre Channel host bus adapter from a virtual machine MyVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the Fibre Channel host bus adapter is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

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

### -Passthru
Specifies that an object is to be passed through to be pipeline representing the removed Fibre Channel host bus adapter.

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

### -VMFibreChannelHba
Specifies one or more Fibre Channel host bus adapters to be removed from a virtual machine.

```yaml
Type: VMFibreChannelHba[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the virtual machine from which the Fibre Channel host bus adapters are to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWideNodeNameSetA
Specifies the World Wide Node name of address set A associated with the Fibre Channel host bus adapter to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWideNodeNameSetB
Specifies the World Wide Node name of address set B associated with the Fibre Channel host bus adapter to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetA
Specifies the World Wide Port name of address set A associated with the Fibre Channel host bus adapter to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetB
Specifies the World Wide Port name of address set B associated with the Fibre Channel host bus adapter to be removed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 5
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

### None
Default

### Microsoft.Virtualization.Powershell.VMFibreChannelHba
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




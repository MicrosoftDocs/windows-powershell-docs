---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/add-vmfibrechannelhba?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VMFibreChannelHba

## SYNOPSIS
Adds a virtual Fibre Channel host bus adapter to a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMFibreChannelHba [-VMName] <String> [-SanName] <String> [-ComputerName <String[]>] [-GenerateWwn]
 [-Passthru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMFibreChannelHba [-VMName] <String> [-SanName] <String> [-ComputerName <String[]>] [-Passthru]
 -WorldWideNodeNameSetA <String> -WorldWideNodeNameSetB <String> -WorldWidePortNameSetA <String>
 -WorldWidePortNameSetB <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-VMFibreChannelHba [-VM] <VirtualMachine[]> [-SanName] <String> [-GenerateWwn] [-Passthru] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-VMFibreChannelHba [-VM] <VirtualMachine[]> [-SanName] <String> [-Passthru] -WorldWideNodeNameSetA <String>
 -WorldWideNodeNameSetB <String> -WorldWidePortNameSetA <String> -WorldWidePortNameSetB <String> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Add-VMFibreChannelHba** cmdlet adds a virtual Fibre Channel host bus adapter to a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMFibreChannelHba -VMName MyVM -SanName Production
```

This example adds the virtual Fibre Channel host bus adapter associated with virtual storage area network Production to a virtual machine named MyVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a virtual Fibre Channel host bus adapter is to be added.
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

### -Passthru
Specifies that an object representing the virtual machine to which the virtual Fibre Channel host bus adapter being added is to be passed through to the pipeline.

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
Specifies the virtual storage area network (SAN) name to associate with this virtual Fibre Channel host bus adapter.
Use the Get-VMSan cmdlet to get a list of all virtual SANs on the host.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine to which the virtual Fibre Channel host bus adapter is to be added.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine to which the virtual Fibre Channel host bus adapter is to be added.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorldWideNodeNameSetA
Specifies the world wide node name of address A associated with the Fibre Channel host bus adapter to be added.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: Wwnn1

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWideNodeNameSetB
Specifies the world wide node name of address B associated with the Fibre Channel host bus adapter to be added.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: Wwnn2

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetA
Specifies the world wide port name of address A associated with the Fibre Channel host bus adapter to be added.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: Wwpn1

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetB
Specifies the world wide port name of address B associated with the Fibre Channel host bus adapter to be added.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: Wwpn2

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerateWwn
Specifies that the world wide names for the Fibre Channel host bus adapter are to be generated automatically.
When specified, the **WorldWideNodeNameSetA**, **WorldWideNodeNameSetB**, **WorldWidePortNameSetA**, and **WorldWidePortNameSetB** parameters cannot be used.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
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

### None

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




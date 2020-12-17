---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Connect-VMSan

## SYNOPSIS
Associates a host bus adapter with a virtual storage area network (SAN).

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Connect-VMSan [-Name] <String> [-ComputerName <String[]>] [-Passthru] -WorldWideNodeName <String[]>
 -WorldWidePortName <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Connect-VMSan [-Name] <String> [-Passthru] -HostBusAdapter <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Connect-VMSan** cmdlet associates a host bus adapter with a virtual storage area network (SAN).

## EXAMPLES

### Example 1
```
PS C:\>Connect-VMSan -Name Production -WorldWideNodeName C003FF0000FFFF00 -WorldWidePortName C003FF5778E50002
```

Associates the virtual storage area network (SAN) named Production with the host bus adapter having the specified world wide node name and world wide port name.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts where the host bus adapter is to be associated with the virtual storage area network (SAN).
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostBusAdapter
Specifies the host bus adapter to be associated with the virtual storage area network (SAN).

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual storage area network (SAN) with which the host bus adapter is to be associated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.SAN** object is to be passed through to the pipeline representing the virtual storage area network (SAN) to be associated with the host bus adapter.

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

### -WorldWideNodeName
Specifies the world wide node name of the host bus adapter to be associated with the virtual storage area network (SAN).

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortName
The port world wide name of the host bus adapter to be associated with the virtual storage area network (SAN).

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
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

### None
Default

### Microsoft.Virtualization.Powershell.SAN
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




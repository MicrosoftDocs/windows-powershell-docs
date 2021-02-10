---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-VMSwitch

## SYNOPSIS
Adds a virtual switch to an Ethernet resource pool.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMSwitch [-Name] <String[]> [-ResourcePoolName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMSwitch [-VMSwitch] <VMSwitch[]> [-ResourcePoolName] <String[]>
```

## DESCRIPTION
The **Add-VMSwitch** cmdlet adds a virtual switch to an Ethernet resource pool.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMSwitch -Name Test -ResourcePoolName "Engineering Department"
```

Adds virtual switch Test to Ethernet resource pool Engineering Department.

### Example 2
```
PS C:\>Get-VMSwitch -Name Test | Add-VMSwitch -ResourcePoolName "Engineering Department"
```

Adds virtual switch Test to Ethernet resource pool Engineering Department.

## PARAMETERS

### -ComputerName


```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual switch to be added.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -ResourcePoolName
Specifies the name of the resource pool to which the virtual switch is to be added.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VMSwitch
Specifies the virtual switch to be added to the Ethernet resource pool.

```yaml
Type: VMSwitch[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### 
None by default; **Microsoft.Virtualization.Powershell.VMNetwork** if **-PassThru** is present.

## NOTES

## RELATED LINKS




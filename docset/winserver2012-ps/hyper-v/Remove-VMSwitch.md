---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmswitch?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMSwitch

## SYNOPSIS
Deletes a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMSwitch [-Name] <String[]> [[-ResourcePoolName] <String[]>] [-ComputerName <String[]>] [-Force]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMSwitch [-VMSwitch] <VMSwitch[]> [[-ResourcePoolName] <String[]>] [-Force]
```

## DESCRIPTION
The **Remove-VMSwitch** cmdlet deletes a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMSwitch "QoS Switch"
```

Removes a virtual switch named Qos Switch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual switch is to be deleted.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

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

### -Force


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

### -Name
Specifies the name of the virtual switch to be deleted.

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
Specifies the name of the resource pool from which the switch is to be deleted.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VMSwitch
Specifies the virtual switch to be deleted.

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

## NOTES

## RELATED LINKS




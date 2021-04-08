---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/rename-vmswitch?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-VMSwitch

## SYNOPSIS
Renames a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-VMSwitch [-Name] <String> [-NewName] <String> [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-VMSwitch [-VMSwitch] <VMSwitch> [-NewName] <String> [-Passthru]
```

## DESCRIPTION
The **Rename-VMSwitch** cmdlet renames a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>Rename-VMSwitch "QoS Switch" -NewName "IIS Switch"
```

Renames virtual switch QoS Switch as IIS Switch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual switch is to be renamed.
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

### -Name
Specifies the name of the virtual switch to be renamed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -NewName
Specifies the name to which the virtual switch is to be renamed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.EthernetSwitch** object is to be passed through to the pipeline representing the virtual switch to be renamed.

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

### -VMSwitch
Specifies the virtual switch to be renamed.

```yaml
Type: VMSwitch
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

### None
Default

### Microsoft.Virtualization.Powershell.EthernetSwitch
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




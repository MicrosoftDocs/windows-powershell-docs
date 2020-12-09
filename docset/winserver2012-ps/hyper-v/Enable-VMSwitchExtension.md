---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Enable-VMSwitchExtension

## SYNOPSIS
Enables one or more extensions on one or more switches.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-VMSwitchExtension [-Name] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-VMSwitchExtension [-Name] <String[]> [-VMSwitchName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Enable-VMSwitchExtension [-Name] <String[]> [-VMSwitch] <VMSwitch[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_4
```
Enable-VMSwitchExtension [-VMSwitchExtension] <VMSwitchExtension[]> [-ComputerName <String[]>]
```

## DESCRIPTION
The **Enable-VMSwitchExtension** cmdlet enables one or more extensions on one or more switches.
You can use the Get-VMSystemSwitchExtension cmdlet to enumerate the virtual switch extensions installed on the system.

## EXAMPLES

### Example 1
```
PS C:\>Enable-VMSwitchExtension -VMSwitchName External -Name "Microsoft Windows Filtering Platform"
```

Enables WFP ("Microsoft Windows Filtering Platform") on a virtual switch named External.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which an extension is to be enabled.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch on which the extension is to be enabled.

```yaml
Type: VMSwitch[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchExtension
Specifies the extension to be disabled.

```yaml
Type: VMSwitchExtension[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchName
Specifies the name of the switch on which the extension is to be enabled.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the network extension to be enabled.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.PowerShell.NetworkExtension

## NOTES

## RELATED LINKS




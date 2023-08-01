---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/disable-vmswitchextension?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-VMSwitchExtension

## SYNOPSIS
Disables one or more extensions on one or more virtual switches.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-VMSwitchExtension [-Name] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-VMSwitchExtension [-Name] <String[]> [-VMSwitchName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-VMSwitchExtension [-Name] <String[]> [-VMSwitch] <VMSwitch[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_4
```
Disable-VMSwitchExtension [-VMSwitchExtension] <VMSwitchExtension[]> [-ComputerName <String[]>]
```

## DESCRIPTION
The **Disable-VMSwitchExtension** cmdlet disables one or more extensions on one or more virtual switches.
You can run Get-VMSystemSwitchExtension to enumerate the virtual switch extensions installed on the system.

## EXAMPLES

### Example 1
```
PS C:\>Disable-VMSwitchExtension -VMSwitchName "Internal Switch" -Name "Microsoft Windows Filtering Platform"
```

Disables WFP ("Microsoft Windows Filtering Platform") on virtual switch Internal Switch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the extension is to be disabled.
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
Specifies the virtual switch on which the extension is to be disabled.

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
Specifies the name of the switch on which the extension is to be disabled.

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
Specifies the name of the extension to be disabled.

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




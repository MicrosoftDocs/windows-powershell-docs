---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmswitchextension?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMSwitchExtension

## SYNOPSIS
Gets the extensions on one or more virtual switches.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMSwitchExtension [-VMSwitchName] <String[]> [[-Name] <String[]>] [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMSwitchExtension [-VMSwitch] <VMSwitch[]> [-ComputerName <String[]>]
```

## DESCRIPTION
The **Get-VMSwitchExtension** cmdlet gets the extensions on one or more virtual switches.
These extensions may be of different types, and may be either enabled or disabled.
Output can be filtered by extension.
The retrieved extension object does not contain embedded objects for features, or an array of feature IDs.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSwitch InternalSwitch | Get-VMSwitchExtension
```

Gets all virtual switch extension available to the virtual switch InternalSwitch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the extensions are to be retrieved.
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

### -Name
Specifies the name of the extension to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -VMSwitch
Specifies the virtual switch from which the extensions are to be retrieved.

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

### -VMSwitchName
Specifies the name of the virtual switch from which the extensions are to be retrieved.

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

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.SwitchExtension

## NOTES

## RELATED LINKS




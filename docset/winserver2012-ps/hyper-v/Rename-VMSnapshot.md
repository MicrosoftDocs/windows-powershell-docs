---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/rename-vmsnapshot?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-VMSnapshot

## SYNOPSIS
Renames a virtual machine snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-VMSnapshot [-Name] <String> [-VMName] <String> [-NewName] <String> [-ComputerName <String[]>]
 [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-VMSnapshot [-VM] <VirtualMachine> [-NewName] <String> [-Passthru] [-Name] <String>
```

### UNNAMED_PARAMETER_SET_3
```
Rename-VMSnapshot [-VMSnapshot] <VMSnapshot> [-NewName] <String> [-Passthru]
```

## DESCRIPTION
The **Rename-VMSnapshot** cmdlet renames a virtual machine snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Rename-VMSnapshot -VMName TestVM -Name "Configuration 2" -NewName "Configuration 2: applied all updates"
```

Renames snapshot Configuration 2 of virtual machine TestVM to Configuration 2: applied all updates.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine snapshot is to be renamed.
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
Specifies the name of the virtual machine snapshot to be renamed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -NewName
Specifies the name to which the virtual machine snapshot is to be renamed.

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
Specifies that a **VMSnapshot** object is to be passed through to the pipeline representing the virtual machine snapshot to be renamed.

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

### -VM
Specifies the virtual machine of which the snapshot is to be renamed.

```yaml
Type: VirtualMachine
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine of which the snapshot is to be renamed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VMSnapshot
Specifies the virtual machine snapshot to be renamed.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_3
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

### VMSnapshot
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/rename-vmsan?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-VMSan

## SYNOPSIS
Renames a virtual storage area network (SAN).

## SYNTAX

```
Rename-VMSan [-Name] <String> [-NewName] <String> [-ComputerName <String[]>] [-Passthru]
```

## DESCRIPTION
The **Rename-VMSan** cmdlet renames a virtual storage area network (SAN).

## EXAMPLES

### Example 1
```
PS C:\>Rename-VMSan -Name Production -NewName Test
```

Renames a virtual storage area network from Production to Test.

## PARAMETERS

### -ComputerName
Specifies the name of the Hyper-V host on which the virtual storage area network (SAN) is to be renamed.
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
Specifies the current name of the virtual storage area network (SAN) to be renamed.

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

### -NewName
Specifies the new name of the virtual storage area network (SAN) to be renamed.

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the renamed virtual storage area network (SAN).

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.PowerShell.SAN
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/test-vhd?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Test-VHD

## SYNOPSIS
Tests a virtual hard disk for any problems that would make it unusable.

## SYNTAX

```
Test-VHD [-Path] <String[]> [-ComputerName <String[]>]
```

## DESCRIPTION
The **Test-VHD** cmdlet tests a virtual hard disk for any problems that would make it unusable.

## EXAMPLES

### Example 1
```
PS C:\>Test-VHD -Path Diff2.vhdx
```

Tests whether the virtual hard disk chain is in a usable state that starts with the virtual hard disk associated with Diff2.vhdx.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual hard disk is to be tested.
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

### -Path
Specifies the path to the virtual hard disk file of the virtual hard disk to be tested.
If a filename or relative path is specified, the new virtual hard disk path is calculated relative to the current working directory.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS




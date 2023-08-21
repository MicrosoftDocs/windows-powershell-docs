---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/new-vfd?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-VFD

## SYNOPSIS
Creates a virtual floppy disk.

## SYNTAX

```
New-VFD [-Path] <String[]> [-ComputerName <String[]>]
```

## DESCRIPTION
The **New-VFD** cmdlet creates a new virtual floppy disk.

## EXAMPLES

### Example 1
```
PS C:\>New-VFD "c:\floppy.vfd"
```

Creates a new virtual floppy drive at the specified path.
This can be then used in the Set-VMFloppyDiskDrive cmdlet to attach the virtual floppy disk to a virtual machine.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts on which the virtual floppy disk is to be created.
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
Specifies the path to the new virtual floppy disk files to be created.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### System.IO.FileInfo

## NOTES

## RELATED LINKS




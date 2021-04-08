---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/mount-vhd?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Mount-VHD

## SYNOPSIS
Mounts one or more virtual hard disks.

## SYNTAX

```
Mount-VHD [-Path] <String[]> [-ComputerName <String[]>] [-NoDriveLetter] [-Passthru] [-ReadOnly]
```

## DESCRIPTION
The **Mount-VHD** cmdlet mounts one or more virtual hard disks.

## EXAMPLES

### Example 1
```
PS C:\>Mount-VHD -Path c:\test\testvhdx.vhdx
```

Mounts a virtual hard disk where the path to the virtual hard disk file is c:\test\testvhdx.vhdx.

### Example 2
```
PS C:\>Mount-VHD -Path c:\test\testvhdx.vhdx -ReadOnly
```

Mounts a virtual hard disk in read-only mode where the path to the virtual hard disk file is c:\test\testvhdx.vhdx.

### Example 3
```
PS C:\>Mount-VHD -Path c:\test\testvhdx -PassThru | Get-Disk | Get-Partition | Get-Volume
```

Attaches a virtual hard disk to the system where the path to the virtual hard disk file is c:\test\testvhdx.vhdx, and gets the volumes associated with it.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a virtual hard disk is to be mounted.
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

### -NoDriveLetter
Specifies that the virtual hard disk is to be mounted without assigning drive letters to the volumes contained within the virtual hard disk.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: FALSE
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual hard disk to be mounted.

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

### -Path
Specifies the path to the virtual hard disk file for the virtual hard disk to be mounted.
If a filename or relative path is specified, the virtual hard disk path is calculated relative to the current working directory.

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

### -ReadOnly
Specifies that the virtual hard disk is to be mounted in read-only mode.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: FALSE
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS




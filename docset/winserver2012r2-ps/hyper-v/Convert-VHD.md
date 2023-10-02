---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/convert-vhd?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-VHD
---

# Convert-VHD

## SYNOPSIS
Converts the format, version type, and block size of a virtual hard disk file.

## SYNTAX

```
Convert-VHD [-Path] <String> [-DestinationPath] <String> [-VHDType <VhdType>] [-ParentPath <String>]
 [-BlockSizeBytes <UInt32>] [-DeleteSource] [-AsJob] [-Passthru] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Convert-VHD** cmdlet converts a virtual hard disk file by copying the data from a source virtual hard disk file to a new virtual hard disk file of a specified format and version type.
The format is determined by the file extension of the specified files, either .vhdx or .vhd.
Conversion is an offline operation; the virtual hard disk must not be attached when the operation is started.

## EXAMPLES

### Example 1
```
PS C:\>Convert-VHD -Path c:\test\testvhd.vhd -DestinationPath c:\test\testvhdx.vhdx
```

This example converts a source VHD to a destination VHDX.
Because the format is determined by the file extension and the default type is determined by the source virtual hard disk when no type is specified, the destination virtual hard disk will be a VHDX-format disk of the same type as the source virtual hard disk.

### Example 2
```
PS C:\>Convert-VHD -Path c:\test\child1vhdx.vhdx -DestinationPath c:\test\child1vhd.vhd -VHDType Differencing -ParentPath c:\test\parentvhd.vhd
```

This example converts a source differencing disk of VHDX format to a destination differencing disk of VHD format that is connected to an existing parent disk.

## PARAMETERS

### -AsJob
Runs the operation as a background job.

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

### -BlockSizeBytes
Specifies the block size, in bytes, of the virtual hard disk after conversion.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual hard disk is to be converted.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeleteSource
Specifies that the source virtual hard disk is to be deleted after the conversion.

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

### -DestinationPath
Specifies the path to the converted virtual hard disk file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentPath
Specifies the parent path for the destination-differencing virtual hard disk file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the converted virtual hard disk.

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
Specifies the path to the virtual hard disk file to be converted.
If a file name or relative path is specified, the path of the converted hard disk path is calculated relative to the current working directory

```yaml
Type: String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VHDType
Specifies the type of the converted virtual hard disk.
Allowed values are **Fixed**, **Dynamic**, and **Differencing**.
The default is determined by the type of source virtual hard disk.

```yaml
Type: VhdType
Parameter Sets: (All)
Aliases: 
Accepted values: Fixed, Dynamic, Differencing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS


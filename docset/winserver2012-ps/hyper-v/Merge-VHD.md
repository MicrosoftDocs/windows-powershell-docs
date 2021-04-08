---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/merge-vhd?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Merge-VHD

## SYNOPSIS
Merges virtual hard disks.

## SYNTAX

```
Merge-VHD [-Path] <String> [[-DestinationPath] <String>] [-AsJob] [-ComputerName <String[]>] [-Force]
 [-Passthru]
```

## DESCRIPTION
The **Merge-VHD** cmdlet merges virtual hard disks in a differencing virtual hard disk chain.
The merge is from a specified source child disk to a specified destination child disk.

Merge is an offline operation; the virtual hard disk chain must not be attached when merge is initiated.

## EXAMPLES

### Example 1
```
PS C:\>Merge-VHD -Path c:\test\Child4.vhdx -DestinationPath c:\test\Child2.vhdx
```

This example merges the virtual hard disk from Child4 to Child2, for a virtual disk chain with Child4 as a child of Child3, Child3 as a child of Child2, Child2 as a child of Child1, and Child1 as a child of Parent, and with the virtual hard disk file for each located in c:\test.
This example merges all data from Child4 and Child3 up to Child2.
Child4.vhdx and Child3.vhdx are not deleted, but are no longer valid virtual hard disk files after the operation.

## PARAMETERS

### -AsJob
Run the cmdlet as a background job.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which virtual hard disks are to be merged.
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

### -DestinationPath
Specifies the path to the child in the virtual hard disk chain that is the destination for the merge command.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force
Runs the cmdlet without prompting for confirmation.

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the merged virtual hard disk.

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
Specifies the path to the child in the virtual hard disk chain that is the source for the merge command.
If a filename or relative path is specified, the virtual hard disk path will be calculated relative to the current working directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: True
```

## INPUTS

### VHDObject

## OUTPUTS

## NOTES

## RELATED LINKS




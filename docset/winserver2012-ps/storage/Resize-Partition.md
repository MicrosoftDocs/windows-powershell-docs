---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 777A539C-AD9E-4BC8-AA99-397F3964EDA8
manager: dansimp
---

# Resize-Partition

## SYNOPSIS
Resizes a partition and the underlying file system.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Resize-Partition [-Size] <UInt64> [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -DriveLetter <Char[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Resize-Partition [-Size] <UInt64> [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Resize-Partition [-Size] <UInt64> [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -DiskId <String[]> -Offset <UInt64[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Resize-Partition [-DiskNumber] <UInt32[]> [-PartitionNumber] <UInt32[]> [-Size] <UInt64> [-AsJob]
 [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Resize-Partition** cmdlet resizes a partition and the underlying file system.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-Partition -DiskNumber 3 -PartitionNumber 2
Disk Number: 3 
 
PartitionNumber  DriveLetter Offset                                        Size Type 
---------------  ----------- ------                                        ---- ---- 
2                D           135266304                                931.39 GB Basic 

Resize the partition to 900GB.
PS C:\>Resize-Partition -DiskNumber 3 -PartitionNumber 2 -Size (900GB)


The partition is now 900GB.
PS C:\>Get-Partition -DiskNumber 3 -PartitionNumber 2
Disk Number: 3 
 
PartitionNumber  DriveLetter Offset                                        Size Type 
---------------  ----------- ------                                        ---- ---- 
2                D           135266304                                   900 GB Basic 

Get the partition sizes.
PS C:\>$size = (Get-PartitionSupportedSize -DiskNumber 3 -PartitionNumber 2)


Resize to the maximum size.
PS C:\>Resize-Partition -DiskNumber 3 -PartitionNumber 2 -Size $size.MaximumSize
```

This example starts with a 931.39 GB partition.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskId
Specifies an ID used to identify a disk in the system.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies the number of the disk.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.

```yaml
Type: Char[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Offset
Specifies the starting offset, in bytes.

```yaml
Type: UInt64[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionNumber
Specifies the number of the partition.
The number of the partition to be resized.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: Number

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Sends items from the interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output. 


                        
To send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

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

### -Size
Specifies the size of the partition to create.
If not specified, then the number will default to **Bytes**.
The acceptable values for this parameter are: **Bytes**, **KB**, **MB**, **GB**, or **TB**.
The size may be defined by a user.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-Partition](./Get-Partition.md)

[Get-PartitionSupportedSize](./Get-PartitionSupportedSize.md)


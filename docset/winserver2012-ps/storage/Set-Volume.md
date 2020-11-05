---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 5B8170FE-9B23-47A6-9976-0E33220ED118
manager: dansimp
---

# Set-Volume

## SYNOPSIS
Sets or changes the file system label of an existing volume.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-Volume [-DriveLetter] <Char[]> [-AsJob] [-CimSession <CimSession[]>] [-NewFileSystemLabel <String>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-Volume [-AsJob] [-CimSession <CimSession[]>] [-NewFileSystemLabel <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -Path <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-Volume [-AsJob] [-CimSession <CimSession[]>] [-NewFileSystemLabel <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -ObjectId <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Set-Volume [-AsJob] [-CimSession <CimSession[]>] [-NewFileSystemLabel <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Set-Volume [-AsJob] [-CimSession <CimSession[]>] [-NewFileSystemLabel <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -FileSystemLabel <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-Volume** cmdlet sets or changes the file system label of an existing volume. 



                      
This cmdlet returns either Success or Failure and corresponding error code as follows. 

Type:   Volume 
Name:   Vol 
Remarks:   InputObj 

Type:   String \[\] 
Name:   Pathname 
Remarks:   Wildcards disabled 

Type:   String \[\] 
Name:   DriveLetter 
Remarks:   InputObj 

Type:   String \[\] 
Name:   FileSystemLabel 
Remarks:   New Label

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-Volume -FileSystemLabel "Test" -NewFileSystemLabel "TestData"
```

This example changes the file system label from test to TestData.

### EXAMPLE 2
```
PS C:\>Format-Volume -InputObject $PartitionObject -FileSystem NTFS -NewFileSystemLabel "TestData" -ClusterSize (8K) -ShortFileNameSupport $False
```

This example uses the specified Partition object as an input to format the volume on this partition with the NTFS file system, using the file system label testdata with a cluster size of 8K, and with short filename support disabled.

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

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.

```yaml
Type: Char[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies the file system label of the object.
The acceptable values for this parameter include: **NTFS** and **ReFS**.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewFileSystemLabel
Specifies a new file system label to be used.

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

### -ObjectId
Specifies an ID representing the object.
The ID is not globally unique.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: Id

Required: True
Position: Named
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

### -Path
Contains valid path information.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-Volume](./Format-Volume.md)

[Get-Volume](./Get-Volume.md)

[Optimize-Volume](./Optimize-Volume.md)

[Repair-Volume](./Repair-Volume.md)


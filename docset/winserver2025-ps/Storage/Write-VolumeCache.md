---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Volume.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/write-volumecache?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Write-VolumeCache
---

# Write-VolumeCache

## SYNOPSIS
Writes the file system cache to disk.

## SYNTAX

### ByDriveLetter (Default)
```
Write-VolumeCache [-DriveLetter] <Char[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [<CommonParameters>]
```

### ById
```
Write-VolumeCache -ObjectId <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [<CommonParameters>]
```

### ByPaths
```
Write-VolumeCache -Path <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### ByLabel
```
Write-VolumeCache -FileSystemLabel <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Write-VolumeCache -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Write-VolumeCache** cmdlet writes the file system cache to disk.
By default, Windows caches file data to be written to disk in a special memory area before writing the data to disk.

This cmdlet enables you to forcibly empty, or flush, the write cache by writing it to disk.

## EXAMPLES

### Example 1: Write the volume cache
```
PS C:\>Write-VolumeCache C
```

This command writes the volume cache for the C: drive.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies an array of letters that identify one or more drives or volumes in the system.
The cmdlet writes the volume cache for the drives or volumes you specify.

```yaml
Type: Char[]
Parameter Sets: ByDriveLetter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies an array of file system labels.
The cmdlet writes the volume cache for the file system labels you specify.

```yaml
Type: String[]
Parameter Sets: ByLabel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId
Specifies an array of IDs, as strings.
The ID is not globally unique.

```yaml
Type: String[]
Parameter Sets: ById
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
Specifies an array of paths.
The cmdlet writes the volume cache for the paths you specify.

```yaml
Type: String[]
Parameter Sets: ByPaths
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
You can use the pipeline operator to pass an array of MSFT_Volume objects to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
If you specify the *PassThru* parameter, this cmdlet returns an object representing the volumes for which you wrote the file system cache to disk.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS


---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Format-Volume

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByDriveLetter (Default)
```
Format-Volume [-DriveLetter] <Char[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-IsDAX <Boolean>] [-NoTrim]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById
```
Format-Volume -ObjectId <String[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-IsDAX <Boolean>] [-NoTrim]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPaths
```
Format-Volume -Path <String[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-IsDAX <Boolean>] [-NoTrim]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLabel
```
Format-Volume -FileSystemLabel <String[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-IsDAX <Boolean>] [-NoTrim]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPartition
```
Format-Volume [-Partition <CimInstance>] [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-IsDAX <Boolean>] [-NoTrim]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Format-Volume -InputObject <CimInstance[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-IsDAX <Boolean>] [-NoTrim]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AllocationUnitSize
{{ Fill AllocationUnitSize Description }}

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: ClusterSize

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
{{ Fill AsJob Description }}

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
{{ Fill CimSession Description }}

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

### -Compress
{{ Fill Compress Description }}

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

### -DisableHeatGathering
{{ Fill DisableHeatGathering Description }}

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

### -DriveLetter
{{ Fill DriveLetter Description }}

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

### -FileSystem
{{ Fill FileSystem Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: FAT, FAT32, exFAT, NTFS, ReFS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystemLabel
{{ Fill FileSystemLabel Description }}

```yaml
Type: String[]
Parameter Sets: ByLabel
Aliases: FriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
{{ Fill Force Description }}

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

### -Full
{{ Fill Full Description }}

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

### -InputObject
{{ Fill InputObject Description }}

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

### -IsDAX
{{ Fill IsDAX Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewFileSystemLabel
{{ Fill NewFileSystemLabel Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: NewFriendlyName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoTrim
{{ Fill NoTrim Description }}

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

### -ObjectId
{{ Fill ObjectId Description }}

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

### -Partition
{{ Fill Partition Description }}

```yaml
Type: CimInstance
Parameter Sets: ByPartition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
{{ Fill Path Description }}

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

### -SetIntegrityStreams
{{ Fill SetIntegrityStreams Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShortFileNameSupport
{{ Fill ShortFileNameSupport Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

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

### -UseLargeFRS
{{ Fill UseLargeFRS Description }}

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.Char[]

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#MSFT_Volume

## NOTES

## RELATED LINKS

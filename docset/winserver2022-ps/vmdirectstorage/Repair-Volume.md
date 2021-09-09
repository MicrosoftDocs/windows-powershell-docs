---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Repair-Volume

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByDriveLetter (Default)
```
Repair-Volume [-DriveLetter] <Char[]> [-OfflineScanAndFix] [-Scan] [-SpotFix] [-DetectLeaks <DetectLeakMode>]
 [-ScratchFile <String>] [-Threads <UInt32>] [-Triage] [-DirectoryIds <UInt64[]>] [-Salvage <SalvageMode>]
 [-ScratchDir <String>] [-TargetFile <String>] [-TargetDir <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById
```
Repair-Volume -ObjectId <String[]> [-OfflineScanAndFix] [-Scan] [-SpotFix] [-DetectLeaks <DetectLeakMode>]
 [-ScratchFile <String>] [-Threads <UInt32>] [-Triage] [-DirectoryIds <UInt64[]>] [-Salvage <SalvageMode>]
 [-ScratchDir <String>] [-TargetFile <String>] [-TargetDir <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPaths
```
Repair-Volume -Path <String[]> [-OfflineScanAndFix] [-Scan] [-SpotFix] [-DetectLeaks <DetectLeakMode>]
 [-ScratchFile <String>] [-Threads <UInt32>] [-Triage] [-DirectoryIds <UInt64[]>] [-Salvage <SalvageMode>]
 [-ScratchDir <String>] [-TargetFile <String>] [-TargetDir <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLabel
```
Repair-Volume -FileSystemLabel <String[]> [-OfflineScanAndFix] [-Scan] [-SpotFix]
 [-DetectLeaks <DetectLeakMode>] [-ScratchFile <String>] [-Threads <UInt32>] [-Triage]
 [-DirectoryIds <UInt64[]>] [-Salvage <SalvageMode>] [-ScratchDir <String>] [-TargetFile <String>]
 [-TargetDir <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Repair-Volume -InputObject <CimInstance[]> [-OfflineScanAndFix] [-Scan] [-SpotFix]
 [-DetectLeaks <DetectLeakMode>] [-ScratchFile <String>] [-Threads <UInt32>] [-Triage]
 [-DirectoryIds <UInt64[]>] [-Salvage <SalvageMode>] [-ScratchDir <String>] [-TargetFile <String>]
 [-TargetDir <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
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

### -DetectLeaks
{{ Fill DetectLeaks Description }}

```yaml
Type: DetectLeakMode
Parameter Sets: (All)
Aliases:
Accepted values: Scan, ScanAndFix, OfflineScanAndFix, QuerySpaceForFix

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryIds
{{ Fill DirectoryIds Description }}

```yaml
Type: UInt64[]
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

### -OfflineScanAndFix
{{ Fill OfflineScanAndFix Description }}

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

### -Salvage
{{ Fill Salvage Description }}

```yaml
Type: SalvageMode
Parameter Sets: (All)
Aliases:
Accepted values: Diagnose, Scan, Copy, ScanAndCopy, QuickScan, QuickScanAndCopy

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scan
{{ Fill Scan Description }}

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

### -ScratchDir
{{ Fill ScratchDir Description }}

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

### -ScratchFile
{{ Fill ScratchFile Description }}

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

### -SpotFix
{{ Fill SpotFix Description }}

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

### -TargetDir
{{ Fill TargetDir Description }}

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

### -TargetFile
{{ Fill TargetFile Description }}

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

### -Threads
{{ Fill Threads Description }}

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

### -Triage
{{ Fill Triage Description }}

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

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.Volume.RepairStatus

## NOTES

## RELATED LINKS

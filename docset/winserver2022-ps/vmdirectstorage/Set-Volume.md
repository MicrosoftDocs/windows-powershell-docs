---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Set-Volume

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByDriveLetterSetLabel (Default)
```
Set-Volume [-NewFileSystemLabel <String>] -DriveLetter <Char> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectSetDedup
```
Set-Volume -InputObject <CimInstance[]> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectSetLabel
```
Set-Volume -InputObject <CimInstance[]> [-NewFileSystemLabel <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByLabelSetLabel
```
Set-Volume [-NewFileSystemLabel <String>] -FileSystemLabel <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPathSetLabel
```
Set-Volume [-NewFileSystemLabel <String>] -Path <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByUniqueIdSetLabel
```
Set-Volume [-NewFileSystemLabel <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdSetDedup
```
Set-Volume -UniqueId <String> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByPathSetDedup
```
Set-Volume -Path <String> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByLabelSetDedup
```
Set-Volume -FileSystemLabel <String> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDriveLetterSetDedup
```
Set-Volume -DriveLetter <Char> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
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

### -DedupMode
{{ Fill DedupMode Description }}

```yaml
Type: DedupMode
Parameter Sets: ByObjectSetDedup, ByUniqueIdSetDedup, ByPathSetDedup, ByLabelSetDedup, ByDriveLetterSetDedup
Aliases:
Accepted values: Disabled, GeneralPurpose, HyperV, Backup, NotAvailable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriveLetter
{{ Fill DriveLetter Description }}

```yaml
Type: Char
Parameter Sets: ByDriveLetterSetLabel, ByDriveLetterSetDedup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FileSystemLabel
{{ Fill FileSystemLabel Description }}

```yaml
Type: String
Parameter Sets: ByLabelSetLabel, ByLabelSetDedup
Aliases: FriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectSetDedup, ByObjectSetLabel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewFileSystemLabel
{{ Fill NewFileSystemLabel Description }}

```yaml
Type: String
Parameter Sets: ByDriveLetterSetLabel, ByObjectSetLabel, ByLabelSetLabel, ByPathSetLabel, ByUniqueIdSetLabel
Aliases: NewFriendlyName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
{{ Fill Path Description }}

```yaml
Type: String
Parameter Sets: ByPathSetLabel, ByPathSetDedup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -UniqueId
{{ Fill UniqueId Description }}

```yaml
Type: String
Parameter Sets: ByUniqueIdSetLabel, ByUniqueIdSetDedup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### System.String

### System.Char

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-FileStorageTier

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByVolumeDriveLetter (Default)
```
Get-FileStorageTier -VolumeDriveLetter <Char> [-PinnedState <PinnedState>]
 [-PinnedStorageTierClass <StorageTierClass>] [-AllocatedStorageTierClass <StorageTierClass>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFilePath
```
Get-FileStorageTier [-PinnedState <PinnedState>] [-PinnedStorageTierClass <StorageTierClass>]
 [-AllocatedStorageTierClass <StorageTierClass>] -FilePath <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVolume
```
Get-FileStorageTier [-PinnedState <PinnedState>] [-PinnedStorageTierClass <StorageTierClass>]
 [-AllocatedStorageTierClass <StorageTierClass>] -Volume <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVolumePath
```
Get-FileStorageTier [-PinnedState <PinnedState>] [-PinnedStorageTierClass <StorageTierClass>]
 [-AllocatedStorageTierClass <StorageTierClass>] -VolumePath <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### -AllocatedStorageTierClass
{{ Fill AllocatedStorageTierClass Description }}

```yaml
Type: StorageTierClass
Parameter Sets: (All)
Aliases:
Accepted values: Capacity, Performance

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

### -FilePath
{{ Fill FilePath Description }}

```yaml
Type: String
Parameter Sets: ByFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PinnedState
{{ Fill PinnedState Description }}

```yaml
Type: PinnedState
Parameter Sets: (All)
Aliases:
Accepted values: Pinned, Unpinned, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PinnedStorageTierClass
{{ Fill PinnedStorageTierClass Description }}

```yaml
Type: StorageTierClass
Parameter Sets: (All)
Aliases:
Accepted values: Capacity, Performance

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

### -Volume
{{ Fill Volume Description }}

```yaml
Type: CimInstance
Parameter Sets: ByVolume
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeDriveLetter
{{ Fill VolumeDriveLetter Description }}

```yaml
Type: Char
Parameter Sets: ByVolumeDriveLetter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VolumePath
{{ Fill VolumePath Description }}

```yaml
Type: String
Parameter Sets: ByVolumePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Char

### System.String

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance[]

## NOTES

## RELATED LINKS

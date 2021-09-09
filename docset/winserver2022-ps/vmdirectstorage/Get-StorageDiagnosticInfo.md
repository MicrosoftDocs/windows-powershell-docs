---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-StorageDiagnosticInfo

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByStorageSubSystem
```
Get-StorageDiagnosticInfo -InputObject <CimInstance> -DestinationPath <String> [-TimeSpan <UInt32>]
 [-ActivityId <String>] [-ExcludeOperationalLog] [-ExcludeDiagnosticLog] [-IncludeLiveDump]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystemFriendlyName
```
Get-StorageDiagnosticInfo [-StorageSubSystemFriendlyName] <String> -DestinationPath <String>
 [-TimeSpan <UInt32>] [-ActivityId <String>] [-ExcludeOperationalLog] [-ExcludeDiagnosticLog]
 [-IncludeLiveDump] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystemName
```
Get-StorageDiagnosticInfo -StorageSubSystemName <String> -DestinationPath <String> [-TimeSpan <UInt32>]
 [-ActivityId <String>] [-ExcludeOperationalLog] [-ExcludeDiagnosticLog] [-IncludeLiveDump]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystemUniqueId
```
Get-StorageDiagnosticInfo -StorageSubSystemUniqueId <String> -DestinationPath <String> [-TimeSpan <UInt32>]
 [-ActivityId <String>] [-ExcludeOperationalLog] [-ExcludeDiagnosticLog] [-IncludeLiveDump]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### -ActivityId
{{ Fill ActivityId Description }}

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
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPath
{{ Fill DestinationPath Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeDiagnosticLog
{{ Fill ExcludeDiagnosticLog Description }}

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

### -ExcludeOperationalLog
{{ Fill ExcludeOperationalLog Description }}

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

### -IncludeLiveDump
{{ Fill IncludeLiveDump Description }}

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
Type: CimInstance
Parameter Sets: ByStorageSubSystem
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystemFriendlyName
{{ Fill StorageSubSystemFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByStorageSubSystemFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageSubSystemName
{{ Fill StorageSubSystemName Description }}

```yaml
Type: String
Parameter Sets: ByStorageSubSystemName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageSubSystemUniqueId
{{ Fill StorageSubSystemUniqueId Description }}

```yaml
Type: String
Parameter Sets: ByStorageSubSystemUniqueId
Aliases: StorageSubSystemId

Required: True
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

### -TimeSpan
{{ Fill TimeSpan Description }}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

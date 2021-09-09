---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Update-StorageProviderCache

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByName (Default)
```
Update-StorageProviderCache [[-Name] <String[]>] [-Manufacturer <String[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### ByUniqueId
```
Update-StorageProviderCache [-UniqueId <String[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### ByURI
```
Update-StorageProviderCache [-Manufacturer <String[]>] [-URI <Uri[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### ByStorageSubSystem
```
Update-StorageProviderCache [-StorageSubSystem <CimInstance>] [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Update-StorageProviderCache -InputObject <CimInstance[]> [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
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

### -DiscoveryLevel
{{ Fill DiscoveryLevel Description }}

```yaml
Type: DiscoveryLevel
Parameter Sets: (All)
Aliases:
Accepted values: Level0, Level1, Level2, Level3, Full

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

### -Manufacturer
{{ Fill Manufacturer Description }}

```yaml
Type: String[]
Parameter Sets: ByName, ByURI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
{{ Fill PassThru Description }}

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

### -RootObject
{{ Fill RootObject Description }}

```yaml
Type: PSReference
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageSubSystem
{{ Fill StorageSubSystem Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubSystem
Aliases:

Required: False
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
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -URI
{{ Fill URI Description }}

```yaml
Type: Uri[]
Parameter Sets: ByURI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.Uri[]

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider

## NOTES

## RELATED LINKS

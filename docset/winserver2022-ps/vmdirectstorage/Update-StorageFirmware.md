---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Update-StorageFirmware

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByPhysicalDiskFriendlyName (Default)
```
Update-StorageFirmware [-FriendlyName] <String> [-ImagePath <String>] [-SlotNumber <UInt16>]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPhysicalDiskUniqueId
```
Update-StorageFirmware -UniqueId <String> [-ImagePath <String>] [-SlotNumber <UInt16>]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPhysicalDisk
```
Update-StorageFirmware -InputObject <CimInstance> [-ImagePath <String>] [-SlotNumber <UInt16>]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageEnclosureUniqueId
```
Update-StorageFirmware -StorageEnclosureUniqueId <String> [-ImagePath <String>] [-SlotNumber <UInt16>]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageEnclosureFriendlyName
```
Update-StorageFirmware [-StorageEnclosureFriendlyName] <String> [-ImagePath <String>] [-SlotNumber <UInt16>]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageEnclosure
```
Update-StorageFirmware -StorageEnclosure <CimInstance> [-ImagePath <String>] [-SlotNumber <UInt16>]
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

### -FriendlyName
{{ Fill FriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByPhysicalDiskFriendlyName
Aliases: PhysicalDiskFriendlyName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ImagePath
{{ Fill ImagePath Description }}

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

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases: PhysicalDisk

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SlotNumber
{{ Fill SlotNumber Description }}

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageEnclosure
{{ Fill StorageEnclosure Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageEnclosure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageEnclosureFriendlyName
{{ Fill StorageEnclosureFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByStorageEnclosureFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageEnclosureUniqueId
{{ Fill StorageEnclosureUniqueId Description }}

```yaml
Type: String
Parameter Sets: ByStorageEnclosureUniqueId
Aliases:

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

### -UniqueId
{{ Fill UniqueId Description }}

```yaml
Type: String
Parameter Sets: ByPhysicalDiskUniqueId
Aliases: PhysicalDiskUniqueId, Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

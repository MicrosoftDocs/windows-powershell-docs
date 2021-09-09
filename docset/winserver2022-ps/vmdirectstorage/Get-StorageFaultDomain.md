---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-StorageFaultDomain

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### EnumerateFaultDomains (Default)
```
Get-StorageFaultDomain [-FriendlyName <String>] [-SerialNumber <String>] [-Type <StorageFaultDomainType>]
 [-PhysicalLocation <String>] [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageSubsystem
```
Get-StorageFaultDomain -StorageSubsystem <CimInstance> [-FriendlyName <String>] [-SerialNumber <String>]
 [-Type <StorageFaultDomainType>] [-PhysicalLocation <String>] [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageFaultDomain
```
Get-StorageFaultDomain -StorageFaultDomain <CimInstance> [-FriendlyName <String>] [-SerialNumber <String>]
 [-Type <StorageFaultDomainType>] [-PhysicalLocation <String>] [-CimSession <CimSession>] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-StorageFaultDomain -VirtualDisk <CimInstance> [-FriendlyName <String>] [-SerialNumber <String>]
 [-PhysicalLocation <String>] [-CimSession <CimSession>] [<CommonParameters>]
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalLocation
{{ Fill PhysicalLocation Description }}

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

### -SerialNumber
{{ Fill SerialNumber Description }}

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

### -StorageFaultDomain
{{ Fill StorageFaultDomain Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageFaultDomain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubsystem
{{ Fill StorageSubsystem Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubsystem
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Type
{{ Fill Type Description }}

```yaml
Type: StorageFaultDomainType
Parameter Sets: EnumerateFaultDomains, ByStorageSubsystem, ByStorageFaultDomain
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack, StorageSite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDisk
{{ Fill VirtualDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
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

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

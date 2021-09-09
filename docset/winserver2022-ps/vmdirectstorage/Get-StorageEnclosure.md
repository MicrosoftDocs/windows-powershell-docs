---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-StorageEnclosure

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByUniqueId (Default)
```
Get-StorageEnclosure [-UniqueId <String[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFriendlyName
```
Get-StorageEnclosure [[-FriendlyName] <String[]>] [[-SerialNumber] <String[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-StorageEnclosure [-Manufacturer <String[]>] [-Model <String[]>] [-HealthStatus <HealthStatus[]>]
 [-PhysicalDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageNode
```
Get-StorageEnclosure [-Manufacturer <String[]>] [-Model <String[]>] [-HealthStatus <HealthStatus[]>]
 [-StorageNode <CimInstance>] [-PhysicallyConnected] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-StorageEnclosure [-Manufacturer <String[]>] [-Model <String[]>] [-HealthStatus <HealthStatus[]>]
 [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
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

### -FriendlyName
{{ Fill FriendlyName Description }}

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HealthStatus
{{ Fill HealthStatus Description }}

```yaml
Type: HealthStatus[]
Parameter Sets: (All)
Aliases:
Accepted values: Healthy, Warning, Unhealthy, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Manufacturer
{{ Fill Manufacturer Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Model
{{ Fill Model Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisk
{{ Fill PhysicalDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicallyConnected
{{ Fill PhysicallyConnected Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ByStorageNode
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
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageNode
{{ Fill StorageNode Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageEnclosure

## NOTES

## RELATED LINKS

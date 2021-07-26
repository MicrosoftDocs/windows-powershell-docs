---
external help file: StorageScripts-help.xml
Module Name: Storage
online version:
schema: 2.0.0
---

# Get-StorageHistory

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByPhysicalDisk
```
Get-StorageHistory -PhysicalDisk <CimInstance> [-Credential <PSCredential>] [-LogFile <String>]
 [-NumberOfHours <UInt32>] [-Disaggregate] [-Errors] [<CommonParameters>]
```

### ByDeviceGuid
```
Get-StorageHistory -DeviceGuid <String> [-LogFile <String>] [-NumberOfHours <UInt32>] [-Disaggregate] [-Errors]
 [<CommonParameters>]
```

### ByDeviceNumber
```
Get-StorageHistory -DeviceNumber <String> [-LogFile <String>] [-NumberOfHours <UInt32>] [-Disaggregate]
 [-Errors] [<CommonParameters>]
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

### -Credential
{{ Fill Credential Description }}

```yaml
Type: PSCredential
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceGuid
{{ Fill DeviceGuid Description }}

```yaml
Type: String
Parameter Sets: ByDeviceGuid
Aliases: DeviceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceNumber
{{ Fill DeviceNumber Description }}

```yaml
Type: String
Parameter Sets: ByDeviceNumber
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disaggregate
{{ Fill Disaggregate Description }}

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

### -Errors
{{ Fill Errors Description }}

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

### -LogFile
{{ Fill LogFile Description }}

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

### -NumberOfHours
{{ Fill NumberOfHours Description }}

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

### -PhysicalDisk
{{ Fill PhysicalDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
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

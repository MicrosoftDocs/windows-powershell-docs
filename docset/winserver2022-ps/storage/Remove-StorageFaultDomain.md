---
external help file: StorageScripts-help.xml
Module Name: Storage
online version:
schema: 2.0.0
---

# Remove-StorageFaultDomain

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByVirtualDisk
```
Remove-StorageFaultDomain [-VirtualDisk] <CimInstance> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDiskFriendlyName
```
Remove-StorageFaultDomain -VirtualDiskFriendlyName <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDiskName
```
Remove-StorageFaultDomain -VirtualDiskName <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDiskUniqueId
```
Remove-StorageFaultDomain -VirtualDiskUniqueId <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageTier
```
Remove-StorageFaultDomain [-StorageTier] <CimInstance> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageTierFriendlyName
```
Remove-StorageFaultDomain -StorageTierFriendlyName <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageTierUniqueId
```
Remove-StorageFaultDomain -StorageTierUniqueId <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
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
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFaultDomainFriendlyNames
{{ Fill StorageFaultDomainFriendlyNames Description }}

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

### -StorageFaultDomains
{{ Fill StorageFaultDomains Description }}

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTier
{{ Fill StorageTier Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageTier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageTierFriendlyName
{{ Fill StorageTierFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByStorageTierFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierUniqueId
{{ Fill StorageTierUniqueId Description }}

```yaml
Type: String
Parameter Sets: ByStorageTierUniqueId
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

### -VirtualDisk
{{ Fill VirtualDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualDiskFriendlyName
{{ Fill VirtualDiskFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByVirtualDiskFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskName
{{ Fill VirtualDiskName Description }}

```yaml
Type: String
Parameter Sets: ByVirtualDiskName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskUniqueId
{{ Fill VirtualDiskUniqueId Description }}

```yaml
Type: String
Parameter Sets: ByVirtualDiskUniqueId
Aliases:

Required: True
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

---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Add-PhysicalDisk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByStoragePool
```
Add-PhysicalDisk [-StoragePool] <CimInstance> -PhysicalDisks <CimInstance[]> [-Usage <Usage>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskUniqueId
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskUniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskName
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskFriendlyName
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskFriendlyName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDisk
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> [-VirtualDisk] <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolUniqueId
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> [-Usage <Usage>] -StoragePoolUniqueId <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolName
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> [-Usage <Usage>] -StoragePoolName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolFriendlyName
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> [-Usage <Usage>] -StoragePoolFriendlyName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
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

### -PhysicalDisks
{{ Fill PhysicalDisks Description }}

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
{{ Fill StoragePool Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
{{ Fill StoragePoolFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByStoragePoolFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolName
{{ Fill StoragePoolName Description }}

```yaml
Type: String
Parameter Sets: ByStoragePoolName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolUniqueId
{{ Fill StoragePoolUniqueId Description }}

```yaml
Type: String
Parameter Sets: ByStoragePoolUniqueId
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

### -Usage
{{ Fill Usage Description }}

```yaml
Type: Usage
Parameter Sets: ByStoragePool, ByStoragePoolUniqueId, ByStoragePoolName, ByStoragePoolFriendlyName
Aliases:
Accepted values: AutoSelect, ManualSelect, HotSpare, Retired, Journal

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

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

---
external help file: StorageBusClientDevice.cdxml-help.xml
Module Name: StorageBusCache
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagebuscache/get-storagebusclientdevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageBusClientDevice
---

# Get-StorageBusClientDevice

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByDeviceState (Default)
```
Get-StorageBusClientDevice [[-DeviceState] <DeviceState[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDeviceType
```
Get-StorageBusClientDevice [[-DeviceType] <DeviceType[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
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
Type: System.Management.Automation.SwitchParameter
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
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceState
{{ Fill DeviceState Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.StorageBusClientDevice.DeviceState[]
Parameter Sets: ByDeviceState
Aliases:
Accepted values: Disconnected, Paused, Draining, Active, Removed

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeviceType
{{ Fill DeviceType Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.StorageBusClientDevice.DeviceType[]
Parameter Sets: ByDeviceType
Aliases:
Accepted values: Disk, Enclosure, StorageScaleUnit

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

```yaml
Type: System.Int32
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

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.StorageBusClientDevice.DeviceState[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.StorageBusClientDevice.DeviceType[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root\wmi\ClusPortDeviceInformation

## NOTES

## RELATED LINKS

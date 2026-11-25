---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: OffloadDataTransferSetting.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-offloaddatatransfersetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OffloadDataTransferSetting
---

# Get-OffloadDataTransferSetting

## SYNOPSIS
Returns offloaded data transfer (ODX) settings for the specified subsystem.

## SYNTAX

```
Get-OffloadDataTransferSetting [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-OffloadDataTransferSetting** cmdlet returns offloaded data transfer (ODX) settings for the specified storage subsystem.

Note: This cmdlet does not return settings for storage arrays that use the Storage Management Initiative Specification (SMI-S) protocol.

## EXAMPLES

### Example 1: Get all ODX settings
```
PS C:\>Get-OffloadDataTransferSetting
```

This example gets all ODX settings for connected storage arrays, not including storage arrays that support ODX using the SMI-S protocol.

### Example 2: Get storage subsystems that have SMPs that support ODX
```
PS C:\>Get-OffloadDataTransferSetting | Get-StorageSubSystem
```

This example displays all storage subsystems on storage management providers that support ODX, not including storage arrays that support ODX using the SMI-S protocol.

### Example 3: Get the ODX settings for a particular storage subsystem
```
PS C:\>$stsubsys = Get-StorageSubsystem -FriendlyName "Big Array"



PS C:\>Get-OffloadDataTransferSetting -StorageSubsystem $stsubsys
```

This example returns the offload data transfer settings for the StorageSubsystem objects returned by Get-StorageSubSystem cmdlet.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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

### -StorageSubSystem
Specifies the storage subsystem for which you want to get ODX settings.
Enter a StorageSubsystem CIM object, which is exposed by the Get-StorageSubSystem cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe a StorageSubsystem object to the *StorageSubsystem* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_OffloadDataTransferSetting
This cmdlet outputs one or more objects that represents the ODX settings for one or more storage subsystems.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageSubSystem](./Get-StorageSubsystem.md)


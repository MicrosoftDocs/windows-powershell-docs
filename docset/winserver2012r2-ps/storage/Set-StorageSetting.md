---
author: Kateyanne
description: 
external help file: StorageSetting.cdxml-help.xml
manager: jasgro
Module Name: Storage
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storage/set-storagesetting?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StorageSetting
---

# Set-StorageSetting

## SYNOPSIS
Adjusts or configures current storage settings of the StorageSetting object.

## SYNTAX

```
Set-StorageSetting [-NewDiskPolicy <NewDiskPolicy>] [-ScrubPolicy <ScrubPolicy>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-StorageSetting** cmdlet adjusts or configures current storage settings of the StorageSetting object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-StorageSetting -NewDiskPolicy OfflineAll
```

This example changes the new disk policy so that all newly attached disks remain offline.

### EXAMPLE 2
```
PS C:\> Set-StorageSetting -NewDiskPolicy OfflineInternal
```

This example changes the new disk policy so that all newly attached disks on a local bus remain offline.

### EXAMPLE 3
```
PS C:\> Set-StorageSetting -NewDiskPolicy OfflineShared
```

This example changes the new disk policy so that all new shared bus disks remain offline and all new local bus disks remain online.

### EXAMPLE 4
```
PS C:\> Set-StorageSetting -NewDiskPolicy OnlineAll
```

This example changes the new disk policy so that all new disks are brought online, regardless of whether the disk are on a local or shared bus.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -NewDiskPolicy
Manages the policy that will be applied to newly attached disks.
New disk policy accepts the following settings; (only applies to disks that were not previously seen), The acceptable values for this parameter are:
  •  OnlineAll: (Same as current diskpartsanpolicy definition) All disks are automatically onlined regardless of bus-type or configuration.
Can cause data loss if used on shared bus disks improperly. 
  •  OfflineAll: (Same as current diskpartsanpolicy definition) All disks are automatically left offline, regardless of the bus-type.
(not recommended for Windows Client as this would result in attached USB disk not being available by default). 
  •  OfflineInternal: Leaves all newly attached disks, which are non-shared storage busses (such as ATA, SATA, USB) offline by default.
(new for Windows Server® 2012). 
  •  OfflineShared: Leaves all newly attached disks which are on a sharable bus (iSCSI, FC, SAS) offline by default.

```yaml
Type: NewDiskPolicy
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, OnlineAll, OfflineShared, OfflineAll, OfflineInternal

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScrubPolicy
Specifies the policy for the files that the automatic data integrity scanner scrubs.
The acceptable values for this parameter are:

- Off: No files are scrubbed.
- Integrity Streams: Only files with integrity streams are scrubbed.
- All: All files are scrubbed.

```yaml
Type: ScrubPolicy
Parameter Sets: (All)
Aliases: 
Accepted values: Off, IntegrityStreams, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-StorageSetting](./Get-StorageSetting.md)


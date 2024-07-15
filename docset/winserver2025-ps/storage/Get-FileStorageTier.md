---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FileStorageTier.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-filestoragetier?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileStorageTier
---

# Get-FileStorageTier

## SYNOPSIS
Gets the files assigned to a Storage tier on a volume, and their status.

## SYNTAX

### ByVolumeDriveLetter (Default)
```
Get-FileStorageTier -VolumeDriveLetter <Char> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVolumePath
```
Get-FileStorageTier -VolumePath <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVolume
```
Get-FileStorageTier -Volume <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFilePath
```
Get-FileStorageTier -FilePath <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-FileStorageTier** cmdlet gets all the files assigned to a Storage tier on a tiered volume stored on a tiered Storage space, and the status of each file.
A file that you assign to a Storage tier is called a pinned file.
The possible status values are the following:

- Not on tier
- Completely on tier
- Partially on tier

## EXAMPLES

### Example 1: Get status for a file
```
PS C:\>Get-FileStorageTier -FilePath "D:\DataFile06.txt"
```

This command gets the pinned file that you specify, and its status.

### Example 2: Get pinned files for a volume
```
PS C:\>Get-FileStorageTier -VolumePath "\\?\Volume{6d6e000d-6038-11e2-be6d-806e6f6e6963}\"
```

This command gets the pinned files for the specified volume, and their status values.

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

### -FilePath
Specifies the full path of a file.
The cmdlet gets the pinned file that you specify and its status.

```yaml
Type: String
Parameter Sets: ByFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Volume
Specifies a volume as a **CimInstance** object.
The cmdlet gets the pinned files for the volume that you specify, and their status values.
To obtain a volume, use the Get-Volume cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVolume
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeDriveLetter
Specifies the drive letter of a volume.
The cmdlet gets the pinned files for the volume that you specify, and their status values.

```yaml
Type: Char
Parameter Sets: ByVolumeDriveLetter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VolumePath
Specifies the path of a volume.
The cmdlet gets the pinned files for the volume that you specify, and their status values.

```yaml
Type: String
Parameter Sets: ByVolumePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MSFT_FileStorageTier
This cmdlet generates a file storage tier object that contains the desired storage tier, file path, status, desired storage tier file size, and state.
State includes values of Ok, Pending, and Processing.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Clear-FileStorageTier](./Clear-FileStorageTier.md)

[Set-FileStorageTier](./Set-FileStorageTier.md)


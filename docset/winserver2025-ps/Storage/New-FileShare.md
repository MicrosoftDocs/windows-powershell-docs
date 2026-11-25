---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FileServer.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/new-fileshare?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileShare
---

# New-FileShare

## SYNOPSIS
Creates an access point for a remote file share.

## SYNTAX

### ByName (Default)
```
New-FileShare -FileServerFriendlyName <String[]> -Name <String> [-Description <String>]
 -SourceVolume <CimInstance> [-RelativePathName <String>] [-ContinuouslyAvailable <Boolean>]
 [-EncryptData <Boolean>] [-Protocol <FileSharingProtocol>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByUniqueId
```
New-FileShare -FileServerUniqueId <String[]> -Name <String> [-Description <String>] -SourceVolume <CimInstance>
 [-RelativePathName <String>] [-ContinuouslyAvailable <Boolean>] [-EncryptData <Boolean>]
 [-Protocol <FileSharingProtocol>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-FileShare -InputObject <CimInstance[]> -Name <String> [-Description <String>] -SourceVolume <CimInstance>
 [-RelativePathName <String>] [-ContinuouslyAvailable <Boolean>] [-EncryptData <Boolean>]
 [-Protocol <FileSharingProtocol>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FileShare** cmdlet creates an access point for a remote file share.

The file share that this cmdlet creates represents a Server Message Block (SMB) or Network File System (NFS) share, which is on top of a MSFT_Volume.

## EXAMPLES

### Example 1: Create an SMB file share
```
PS C:\>$Pool = Get-StoragePool -FriendlyName "clusteredpool"
PS C:\> $Volume = $Pool | New-Volume -FriendlyName "myvol" -UseMaximumSize $True
PS C:\> New-FileShare -Name "Docs" -FileServerFriendlyName "scaleout-clus" -SourceVolume $Volume -IsContinuouslyAvailable $True -Protocol SMB
```

The first command gets the specified storage pool, and then stores it in the $Pool variable.

The second command creates a volume using the storage pool in $Pool, and then stores it in the $Volume variable.

The third command creates a continuously available SMB file share using the volume in $SourceVolume.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContinuouslyAvailable
Indicates whether the file share is continuously available.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a user-friendly description of the file share.

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

### -EncryptData
Indicates whether to encrypt the data on transport.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileServerFriendlyName
Specifies the name of the file server to host the file share.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileServerUniqueId
Specifies the unique ID of the file server.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the file share to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the file sharing protocol.
The acceptable values for this parameter are:

- NFS
- SMB

```yaml
Type: FileSharingProtocol
Parameter Sets: (All)
Aliases:
Accepted values: NFS, SMB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RelativePathName
Specifies the relative path.
Specify this parameter if the path for the new file share is not the root of the volume.

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

### -SourceVolume
Specifies the source volume.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MSFT_FileShare

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Debug-FileShare](./Debug-FileShare.md)

[Get-FileShare](./Get-FileShare.md)

[Remove-FileShare](./Remove-FileShare.md)

[Set-FileShare](./Set-FileShare.md)


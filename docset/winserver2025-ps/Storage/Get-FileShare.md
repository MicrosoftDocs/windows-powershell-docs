---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FileShare.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-fileshare?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileShare
---

# Get-FileShare

## SYNOPSIS
Retrieves file share objects and their properties.

## SYNTAX

### ByFileServer (Default)
```
Get-FileShare [-Name <String[]>] [-Protocol <FileSharingProtocol[]>] [-FileServer <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-FileShare [-UniqueId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVolume
```
Get-FileShare [-Name <String[]>] [-Protocol <FileSharingProtocol[]>] [-Volume <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BySubsystem
```
Get-FileShare [-Name <String[]>] [-Protocol <FileSharingProtocol[]>] [-Subsystem <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-FileShare** cmdlet gets objects that correspond to the file shares on the specified server.
You must have local administrator credentials on a server to retrieve the objects.

## EXAMPLES

### Example 1: Get all file shares on the local server
```
PS C:\>Get-FileShare
```

This command lists all the file shares on the local server.
You must have local administrator permissions on the server to run this command.

### Example 2: Get all NFS file shares on the specified file server
```
PS C:\>Get-FileShare -Protocol NFS -FileServer (Get-StorageFileServer -FriendlyName "FileServer01")
```

This command lists all NFS file shares on the file server named FileServer01.
You must have local administrator credentials on the server to run this command.
The command gets the file server by using the **Get-StorageFileServer** cmdlet.

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

### -FileServer
Specifies the file server on which the file share is hosted.
To obtain a **FileServer**, use the Get-StorageFileServer cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByFileServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the file share to get.

```yaml
Type: String[]
Parameter Sets: ByFileServer, ByVolume, BySubsystem
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the file sharing protocol of the file shares that this cmdlet gets.
The acceptable values for this parameter are: SMB and NFS.

```yaml
Type: FileSharingProtocol[]
Parameter Sets: ByFileServer, ByVolume, BySubsystem
Aliases:
Accepted values: NFS, SMB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subsystem
Specifies the storage subsystem from which to get file shares.
To obtain a **StorageSubsystem** object, use the Get-StorageSubSystem cmdlet.

```yaml
Type: CimInstance
Parameter Sets: BySubsystem
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

### -UniqueId
Specifies a unique ID.

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

### -Volume
Specified the volume object that contains the file share to get.
To obtain a volume, use the Get-Volume cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVolume
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageFileServer](./Get-StorageFileServer.md)

[Get-StorageSubSystem](./Get-StorageSubsystem.md)

[Get-Volume](./Get-Volume.md)


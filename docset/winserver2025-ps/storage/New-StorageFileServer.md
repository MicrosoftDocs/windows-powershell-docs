---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageSubSystem.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/new-storagefileserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-StorageFileServer
---

# New-StorageFileServer

## SYNOPSIS
Creates a storage file server.

## SYNTAX

### ByFriendlyName (Default)
```
New-StorageFileServer [-StorageSubSystemFriendlyName] <String[]> -HostNames <String[]>
 -Protocols <FileSharingProtocol[]> [-FriendlyName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-StorageFileServer -StorageSubSystemUniqueId <String[]> -HostNames <String[]>
 -Protocols <FileSharingProtocol[]> [-FriendlyName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
New-StorageFileServer -StorageSubSystemName <String[]> -HostNames <String[]> -Protocols <FileSharingProtocol[]>
 [-FriendlyName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-StorageFileServer -InputObject <CimInstance[]> -HostNames <String[]> -Protocols <FileSharingProtocol[]>
 [-FriendlyName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-StorageFileServer** cmdlet creates a file server for a specified Storage subsystem exposed by a Storage provider.
For Windows network-attached storage (NAS), this cmdlet enables the necessary roles and features to implement a scale-out file server instance on a cluster.

Not all systems support file servers other than the default.

## EXAMPLES

### Example 1: Create a file server
```
PS C:\>New-StorageFileServer -FriendlyName "SalesFiles" -StorageSubSystemFriendlyName "Sales-cluster" -HostName "salesfiles" -Protocol SMB -ContinuouslyAvailabe $True
```

This command creates a scale-out file server on the sales-cluster subsystem.

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

### -FriendlyName
Specifies a friendly name for the file server.
A friendly name is not required to be unique.

Some Storage subsystems do not allow a friendly name when creating a file server.
In this scenario, the file server may be assigned a friendly name by this operation.

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

### -HostNames
Specifies an array of names of access points for the file server.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -Protocols
Specifies the file sharing protocol.
Valid values are: SMB, NFS, or both.

```yaml
Type: FileSharingProtocol[]
Parameter Sets: (All)
Aliases:
Accepted values: NFS, SMB

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageSubSystemFriendlyName
Specifies the friendly name of the Storage subsystem to host the file server.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemName
Specifies the name of the Storage subsystem to host the file server.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemUniqueId
Specifies the unique ID of the Storage subsystem to host the file server.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StorageSubSystemId

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_StorageFileServer

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageFileServer](./Get-StorageFileServer.md)

[Remove-StorageFileServer](./Remove-StorageFileServer.md)

[Set-StorageFileServer](./Set-StorageFileServer.md)


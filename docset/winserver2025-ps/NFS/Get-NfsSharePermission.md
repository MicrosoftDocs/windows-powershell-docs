---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/get-nfssharepermission?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NfsSharePermission
---

# Get-NfsSharePermission

## SYNOPSIS
Gets information about permissions that an NFS server grants to exported NFS shares.

## SYNTAX

### ByName (Default)
```
Get-NfsSharePermission [[-ClientName] <String>] [[-ClientType] <String>] [[-Permission] <String>]
 [-Name] <String> [-NetworkName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByPath
```
Get-NfsSharePermission [-Path] <String> [[-ClientName] <String>] [[-ClientType] <String>]
 [[-Permission] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NfsSharePermission** cmdlet gets information about access permissions granted by a Network File System (NFS) server that has an NFS share configured.

## EXAMPLES

### Example 1: Get all permissions for a specified NFS share
```
PS C:\> Get-NfsSharePermission -Name "Export"
ClientName        : All Machines
ClientType        : Built-in Group
Name              : Export
Path              : C:\shares\Export
Permission        : READ, WRITE
AllowRootAccess   : ALLOW ACCESS
LanguageEncoding  : ansi
```

This command gets the permissions for an NFS share named Export.

### Example 2: Get read/write permissions for a specified NFS share
```
PS C:\> Get-NfsSharePermission -Name "Export" -Permission "readwrite"
```

This command gets the read/write permissions for an NFS share named Export.

## PARAMETERS

### -AsJob
Indicates that this cmdlet runs the command as a background job on a remote computer.
Use this parameter to run commands that take an extensive time to finish.

When you use the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.
You can continue to work in the session while the job finishes.
To manage the job, use the **Job** cmdlets.
To get the job results, use the Receive-Job cmdlet.

The *AsJob* parameter resembles using the Invoke-Command cmdlet to run a Start-Job command remotely.
However, with *AsJob*, the job is created on the local computer, even though the job runs on a remote computer, and the results of the remote job are automatically returned to the local computer.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251) and [about_Remote_Jobs](https://go.microsoft.com/fwlink/?LinkID=135184).

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

### -ClientName
Specifies a client name.
The client name can be a host name or IP address, netgroup name, or client group name.
To specify the type of client, use the *ClientType* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Client

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientType
Specifies a client type.
The acceptable values for this parameter are:

- host
- clientgroup
- netgroup

```yaml
Type: String
Parameter Sets: (All)
Aliases: Type
Accepted values: host, netgroup, clientgroup, builtin

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an NFS share.

```yaml
Type: String
Parameter Sets: ByName
Aliases: ShareName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkName
Specifies the scoped network name of an NFS share.

On a local share, *NetworkName* is the host name.
On a cluster, it is the network name in the resource group to which the share is scoped.

```yaml
Type: String
Parameter Sets: ByName
Aliases: netname

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path of an NFS share.

```yaml
Type: String
Parameter Sets: ByPath
Aliases: SharePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permission
Specifies the type of access to get for an NFS share.
The acceptable values for this parameter are:

- no-access
- readonly
- readwrite

A client can have either read-only or read/write access.
Only the All Machines group can have all three types of access.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Access
Accepted values: no-access, readonly, readwrite

Required: False
Position: 3
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

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/nfs/MSFT_NfsSharePermission

## NOTES

## RELATED LINKS

[Grant-NfsSharePermission](./Grant-NfsSharePermission.md)

[Revoke-NfsSharePermission](./Revoke-NfsSharePermission.md)


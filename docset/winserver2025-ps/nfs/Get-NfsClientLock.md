---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsClientLock.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/get-nfsclientlock?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NfsClientLock
---

# Get-NfsClientLock

## SYNOPSIS
Gets file locks that a client computer holds on an NFS server.

## SYNTAX

### v4 (Default)
```
Get-NfsClientLock [[-Path] <String[]>] [[-LockType] <ClientLockType[]>] [[-StateId] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### v3
```
Get-NfsClientLock [[-Path] <String[]>] [[-LockType] <ClientLockType[]>] [[-ComputerName] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NfsClientLock** cmdlet gets locks that client computers hold for files that a Network File System (NFS) server shares.

For NFS v3 protocol locks, this cmdlet gets NFS client locks based on the list of client computers that hold locks to a particular file, and the list of files that a particular client computer has locked.

For NFS v4 protocol locks, this cmdlet gets NFS client locks based on the list of files that a particular client computer has locked, and the state identifiers of the locked files.

You can also use the *LockType* parameter to get locked files on an NFS server based on the NFS protocol that the NFS client uses.

## EXAMPLES

### Example 1: Get locked files on a local NFS server
```
PS C:\> Get-NfsClientLock -Path "c:\shares\NFSshare01\*"
```

This command gets all the locked files on a local NFS server that have a path that begins with C:\shares\NFSshare01\.

### Example 2: Get locked files on a NFS server that have NLM lock type
```
PS C:\>Get-NfsClientLock -LockType NLM
```

This command gets all the locked files on the server that have a NLM lock type.

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

### -ComputerName
Specifies the host name of a computer that holds a lock to files on the NFS server.
All the locks that the specified computer holds are enumerated.

```yaml
Type: String
Parameter Sets: v3
Aliases: client, name, ClientComputer

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LockType
Specifies an array of lock types.
**Get-NfsClientLock** gets files that have the specified lock types.
Valid values are NLM and NFS.

Locks acquired by NFS clients that mount files to an NFS share by using the NFS v2 or the NFS v3 protocol are Network Lock Manager (NLM) locks.
Locks acquired by NFS clients that mount files by using the NFS v4.1 protocol are NFS locks.

```yaml
Type: ClientLockType[]
Parameter Sets: (All)
Aliases: type
Accepted values: NLM, NFS

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies an array of paths and file names on the NFS server.
**Get-NfsClientLock** gets the locked files on an NFS server that have the specified paths.
If there are multiple clients that have multiple locks on the same file, all the locks are revoked.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: LockedFile, file

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StateId
Specifies the state identifier of the locks on the NFS server.
*StateId* applies only to locks that an NFS client acquires by using the NFS v4.1 protocol.

```yaml
Type: String
Parameter Sets: v4
Aliases:

Required: False
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsNlmClientLock, Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_Nfsv4ClientLock

## NOTES

## RELATED LINKS

[Revoke-NfsClientLock](./Revoke-NfsClientLock.md)


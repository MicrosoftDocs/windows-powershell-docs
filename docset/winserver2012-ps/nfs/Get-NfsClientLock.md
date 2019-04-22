---
external help file: NFS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 8C029D0B-7CC0-4C84-B3B0-57AFE0153F56
manager: dansimp
---

# Get-NfsClientLock

## SYNOPSIS
Gets file locks that a client computer holds on an NFS server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NfsClientLock [[-Path] <String[]>] [[-LockType] <ClientLockType[]>] [[-StateId] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NfsClientLock [[-Path] <String[]>] [[-LockType] <ClientLockType[]>] [[-ComputerName] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NfsClientLock** cmdlet gets locks that client computers hold for files that a Network File System (NFS) server shares.

For NFS v3 protocol locks, this cmdlet gets NFS client locks based on the list of client computers that hold locks to a particular file, and the list of files that a particular client computer has locked.

For NFS v4 protocol locks, this cmdlet gets NFS client locks based on the list of files that a particular client computer has locked, and the state identifiers of the locked files.

You can also use the **LockType** parameter to get locked files on an NFS server based on the NFS protocol that the NFS client uses.

## EXAMPLES

### Example 1: Get locked files on a local NFS server
```
PS C:\> Get-NfsClientLock -Path c:\shares\NFSshare01\*
```

This command gets all the locked files on a local NFS server that have a path that begins with C:\shares\NFSshare01\.

### Example 2: Get locked files on a NFS server that have NLM lock type
```
PS C:\>Get-NfsClientLock -LockType NLM
```

This command gets all the locked files on the server that have a NLM lock type.

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
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 3
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
Aliases: 

Required: False
Position: 2
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
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StateId
Specifies the state identifier of the locks on the NFS server.
**StateId** applies only to locks that an NFS client acquires by using the NFS v4.1 protocol.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsNlmClientLock, Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_Nfsv4ClientLock

## NOTES

## RELATED LINKS

[Revoke-NfsClientLock](./Revoke-NfsClientLock.md)


---
external help file: MSFT_NfsClientLock.cmdletDefinition.cdxml-help.xml
Module Name: NFS
online version: 
schema: 2.0.0
title: Revoke-NfsClientLock
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 3E674637-CC4D-43AF-B051-71728F09F909
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Revoke-NfsClientLock

## SYNOPSIS
Releases file locks that a client computer holds on an NFS server.

## SYNTAX

### v4 (Default)
```
Revoke-NfsClientLock [-Path] <String[]> [[-LockType] <ClientLockType[]>] [[-StateId] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### v3
```
Revoke-NfsClientLock [-Path] <String[]> [[-LockType] <ClientLockType[]>] [[-ComputerName] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Revoke-NfsClientLock -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-NfsClientLock** cmdlet releases locks that a client computer currently holds for files that a Network File System (NFS) server shares.
You can select the locks to revoke by specifying the path of the files.
The **Path** parameter supports wildcards, so you can revoke multiple locks that match the specified pattern.

You can revoke NFS v4 protocol locks by specifying the state identifier of the locked files.
You can revoke NFS v3 protocol locks by specifying the computer name of the NFS client that holds the lock on the files.

## EXAMPLES

### Example 1: Revoke the lock on all files
```
PS C:\> Revoke-NfsClientLock -Path c:\shares\*
```

This command revokes the lock on all the files on a local NFS server that have a path that begins with c:\shares\.

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

### -ComputerName
Specifies the host name of the client computer that holds a lock to files on the NFS server.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -LockType
Specifies an array of lock types on the file.
Valid values are NLM and NFS.

Locks acquired by NFS clients that mount files to an NFS share by using the NFS v2 or the NFS v3 protocol are Network Lock Manager (NLM) locks.
Locks acquired by NFS clients that mount files by using the NFS v4.1 protocol are NFS locks.

```yaml
Type: ClientLockType[]
Parameter Sets: v4, v3
Aliases: type
Accepted values: NLM, NFS

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Path
Specifies an array of paths and file names on the NFS server.
If there are multiple clients that have multiple locks on the same file, all the locks are revoked.

```yaml
Type: String[]
Parameter Sets: v4, v3
Aliases: file, LockedFile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StateId
Specifies the state identifier of the locks to revoke.
**StateId** applies only to locks that an NFS client acquires by using the NFS v4.1 protocol.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsClientLock](./Get-NfsClientLock.md)


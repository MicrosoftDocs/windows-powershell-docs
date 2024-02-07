---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsStatistics.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/get-nfsstatistics?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NfsStatistics
---

# Get-NfsStatistics

## SYNOPSIS
Gets RPC call statistics that an NFS server maintains.

## SYNTAX

```
Get-NfsStatistics [-Protocol <String[]>] [-Name <String[]>] [-Version <UInt32[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NfsStatistics** cmdlet gets remote procedure call (RPC) statistics that a Network File System (NFS) server maintains for requests served over the following protocols:

- Mount v1 protocol
- Mount v3 protocol
- NFS v2 protocol
- NFS v3 protocol
- NFS v4.1 protocol

## EXAMPLES

### Example 1: Get all NFS statistics on a local NFS server
```
PS C:\>Get-NfsStatistics
```

This command lists all available statistics, including all protocols and versions, on a local NFS server.

### Example 2: Get NFS statics for the Mount protocol on a local NFS server
```
PS C:\> Get-NfsStatistics -Protocol "Mount"
Name of Statistic                       Protocol                       Version                        Value
-----------------                       --------                       -------                        -----
V1_MNT_NULL                               MOUNT                           1                            132
V1_MNT_MOUNT                              MOUNT                           1                             0
V1_MNT_DUMPMOUNT                          MOUNT                           1                             0
V1_MNT_UNMOUNT                            MOUNT                           1                             1
V1_MNT_UNMOUNTALL                         MOUNT                           1                             0
V1_MNT_EXPORTLIST                         MOUNT                           1                             2
V3_MNT_NULL                               MOUNT                           3                            15
V3_MNT_MOUNT                              MOUNT                           3                            45
V3_MNT_DUMPMOUNT                          MOUNT                           3                             0
V3_MNT_UNMOUNT                            MOUNT                           3                             0
V3_MNT_UNMOUNTALL                         MOUNT                           3                            10
V3_MNT_EXPORTLIST                         MOUNT                           3                            22
```

This command gets call statistics for the Mount protocol only.

### Example 3: Get call statistics for version 1 of the Mount protocol
```
PS C:\>Get-NfsStatistics -Protocol "Mount" -Version 1
```

This command gets call statistics for version 1 of the Mount protocol.

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

### -Name
Specifies the name of one or more counters to get.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the type of protocol for which to get NFS statistics.
Valid values are:

- NFS
- Mount

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

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

### -Version
Specifies the version of protocol for which to get NFS statistics.
Valid NFS protocol versions are 2, 3, and 4.
Valid Mount protocol versions are 1 and 3.

```yaml
Type: UInt32[]
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsStatistics

## NOTES

## RELATED LINKS

[Reset-NfsStatistics](./Reset-NfsStatistics.md)


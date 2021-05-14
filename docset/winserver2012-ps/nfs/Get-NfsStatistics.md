---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://docs.microsoft.com/powershell/module/nfs/get-nfsstatistics?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NfsStatistics

## SYNOPSIS
Gets RPC call statistics that an NFS server maintains.

## SYNTAX

```
Get-NfsStatistics [-AsJob] [-CimSession <CimSession[]>] [-Name <String[]>] [-Protocol <String[]>]
 [-ThrottleLimit <Int32>] [-Version <UInt32[]>]
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

### Example 2: Get NFS statics for the MOUNT protocol on a local NFS server
```
PS C:\> Get-NfsStatistics -Protocol "MOUNT"

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

### Example 3:
```
PS C:\>Get-NfsStatistics -Protocol "MOUNT" -Version 1
```

This command gets call statistics for version 1 of the Mount protocol.

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
Accept wildcard characters: True
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsStatistics

## NOTES

## RELATED LINKS

[Reset-NfsStatistics](./Reset-NfsStatistics.md)


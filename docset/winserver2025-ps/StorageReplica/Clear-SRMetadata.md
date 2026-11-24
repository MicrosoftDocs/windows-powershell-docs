---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/clear-srmetadata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-SRMetadata
---

# Clear-SRMetadata

## SYNOPSIS
Removes unreferenced Storage Replica metadata.

## SYNTAX

### RG (Default)
```
Clear-SRMetadata [[-ComputerName] <String>] [-NoRestart] [-Force] [-Name] <String> [-Logs] [-Partition]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AllServer
```
Clear-SRMetadata [[-ComputerName] <String>] [-AllConfiguration] [-AllLogs] [-AllPartitions] [-NoRestart]
 [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Clear-SRMetadata** cmdlet removes unreferenced Storage Replica metadata from the registry, partition, and System Volume Information folder.
This orphaned metadata may exist after a failed partnership or replication group removal.

Do not run this cmdlet unless you have already tried to clean up by using the Remove-SRPartnership and Remove-SRGroup cmdlets.

## EXAMPLES

### Example 1: Delete all unreferenced log files
```
PS C:\>Clear-SRMetadata -AllLogs
Confirm
Are you sure you want to perform this action?
Clearing orphaned log files from Storage Replica log container. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
```

This command deletes all unreferenced log files from all log volumes on the computer.

### Example 2: Delete unreferenced log files partition database entries
```
PS C:\>Clear-SRMetadata -AllLogs -AllPartitions -Verbose
Confirm
Are you sure you want to perform this action?
Clearing orphaned log files from Storage Replica log container. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
VERBOSE: Looking for orphaned Storage Replica logs on volume \\?\Volume{c9406624-d9e8-489d-9f29-e95c02bc13f9}\...
VERBOSE: 1 orphaned log directories were deleted.
VERBOSE: 4 orphaned log files were deleted.
VERBOSE: Looking for orphaned records in Storage Replica partition database.
VERBOSE: No orphan records found in Storage Replica partition database.
```

This command deletes all unreferenced log files from all log volumes and unreferenced partition database entries from all data volumes on the computer.
In this example you see that several log files were deleted.

### Example 3: Clear logs for a replication group
```
This command gets the name of all the replication groups on the current computer by using the Format-List cmdlet. There is only one replication group on this computer.
PS C:\>Get-SRGroup | Format-List -Property "name"
Name               : ReplicationGroup01

This command clears all logs for a replication group found in the first command. The command reports verbose output.
PS C:\>Clear-SRMetadata -Name "ReplicationGroup01" -Logs -Verbose
Confirm
Are you sure you want to perform this action?
Clearing orphaned log files from Storage Replica log container. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
VERBOSE: Looking for orphaned Storage Replica logs on volume e:\...
VERBOSE: 1 orphaned log directories were deleted.
VERBOSE: 16 orphaned log files were deleted.
```

This example clears all logs for a specific replication group and reports verbose output.

## PARAMETERS

### -AllConfiguration
Indicates that this cmdlet removes all unreferenced Storage Replica registry and cluster resource entries.
This parameter does not affect unclustered hosts.

```yaml
Type: SwitchParameter
Parameter Sets: AllServer
Aliases: AC

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllLogs
Indicates that this cmdlet removes all unreferenced Storage Replica logs from the hidden System Volume Information folders on all log drives.

```yaml
Type: SwitchParameter
Parameter Sets: AllServer
Aliases: AL

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllPartitions
Indicates that this cmdlet removes all unreferenced Storage Replica partition databases from all data drives.

```yaml
Type: SwitchParameter
Parameter Sets: AllServer
Aliases: AP

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -ComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN).
The default value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Logs
Indicates that this cmdlet removes the unreferenced Storage Replica logs from the hidden System Volume Information folders on the log drive for the replication group specified by the *Name* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: RG
Aliases: LO

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the replication group for which this cmdlet clears data.

```yaml
Type: String
Parameter Sets: RG
Aliases: N

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRestart
Indicates that the computer does not restart after the cmdlet removes the entries.
By default, the computer restarts.
We do not support continuing to operate the computer and its storage after metadata cleanup.
Restart as soon as possible.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: NR

Required: False
Position: 98
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Partition
Indicates that this cmdlet removes all unreferenced Storage Replica partition databases from the data drives associated with the replication group specified by *Name*.

```yaml
Type: SwitchParameter
Parameter Sets: RG
Aliases: PA

Required: False
Position: 4
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

## NOTES

## RELATED LINKS

[Remove-SRPartnership](./Remove-SRPartnership.md)

[Remove-SRGroup](./Remove-SRGroup.md)


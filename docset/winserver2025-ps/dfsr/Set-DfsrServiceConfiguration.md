---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/set-dfsrserviceconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsrServiceConfiguration
---

# Set-DfsrServiceConfiguration

## SYNOPSIS
Modifies settings for the DFS Replication service.

## SYNTAX

```
Set-DfsrServiceConfiguration [[-ComputerName] <String[]>] [[-RPCPort] <UInt32>] [[-DisableDebugLog] <Boolean>]
 [[-MaximumDebugLogFiles] <UInt32>] [[-DebugLogPath] <String>] [[-DebugLogSeverity] <UInt32>]
 [[-MaximumDebugLogMessages] <UInt32>] [[-UnexpectedAutoRecovery] <Boolean>]
 [[-CleanupStagingFolderAtPercent] <UInt32>] [[-CleanupStagingFolderUntilPercent] <UInt32>]
 [[-CleanupConflictFolderAtPercent] <UInt32>] [[-CleanupConflictFolderUntilPercent] <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsrServiceConfiguration** cmdlet modifies settings for the Distributed File System (DFS) Replication service on replication group members.
Members of a replication group host replicated folders.
Use this cmdlet to configure cleanup settings, debug logging settings, and automatic recovery for unexpected shut down.

DFS Replication stores files in a folder named ConflictsAndDeleted until it deletes them for space.
DFS Replication can stage files in a staging folder.
In both cases, you can set a maximum folder size, called a quota, by using the **Set-DfsrMembership** cmdlet.
Use the current cmdlet to set the percent of the quota used to start and stop deletion of older files.

By default, DFS Replication enables debug logging.
You can disable logging.
You can also change the number of lines written to each log file, the severity of messages written to log files, the number of log files to keep, and the location to store log files.

## EXAMPLES

### Example 1: Configure a computer to use a dynamic RPC port
```
PS C:\> Set-DfsrServiceConfiguration -RPCPort 0
ComputerName                      : SRV01
RPCPort                           :
DynamicRPCPort                    : True
DisableDebugLog                   : False
MaximumDebugLogFiles              : 1000
DebugLogPath                      : C:\Windows\debug
DebugLogSeverity                  : 4
MaximumDebugLogMessages           : 200000
UnexpectedAutoRecovery            : False
CleanupStagingFolderAtPercent     : 90
CleanupStagingFolderUntilPercent  : 60
CleanupConflictFolderAtPercent    : 90
CleanupConflictFolderUntilPercent : 60
```

This command configures the local computer to use a dynamic RPC port for DFS Replication.
A value of zero (0) or $Null for the *RPCPort* parameter configures the computer to use a dynamic port.

### Example 2: Configure all members to log messages with specific severity
```
PS C:\> Get-DfsrMember | Set-DfsrServiceConfiguration -DebugLogSeverity 5
ComputerName                      : SRV01
RPCPort                           :
DynamicRPCPort                    : True
DisableDebugLog                   : False
MaximumDebugLogFiles              : 1000
DebugLogPath                      : C:\Windows\debug
DebugLogSeverity                  : 5
MaximumDebugLogMessages           : 200000
UnexpectedAutoRecovery            : False
CleanupStagingFolderAtPercent     : 90
CleanupStagingFolderUntilPercent  : 60
CleanupConflictFolderAtPercent    : 90
CleanupConflictFolderUntilPercent : 60

ComputerName                      : SRV02
RPCPort                           :
DynamicRPCPort                    : True
DisableDebugLog                   : True
MaximumDebugLogFiles              : 1000
DebugLogPath                      : C:\Windows\debug
DebugLogSeverity                  : 5
MaximumDebugLogMessages           : 200000
UnexpectedAutoRecovery            : False
CleanupStagingFolderAtPercent     : 90
CleanupStagingFolderUntilPercent  : 60
CleanupConflictFolderAtPercent    : 90
CleanupConflictFolderUntilPercent : 60
```

This command configures all members of all replication groups to log messages with a severity of five (5).
The command gets all members of all replication groups by using the **Get-DfsrMember** cmdlet.
The command passes these members to the **Set-DfsrServiceConfiguration** cmdlet by using the pipeline operator.
That cmdlet changes the severity level for debug logging to five.
The command modifies two member computers.
The console displays the two members found, including the new setting for severity.

## PARAMETERS

### -CleanupConflictFolderAtPercent
Specifies a percent value from 80 to 100.
The default value is 90.

When the ConflictsAndDeleted folder size reaches this percent of the ConflictsAndDeleted quota, the DFS Replication service deletes the oldest files until the folder size falls below a set percent of the quota.
You can specify that percent value by using the *CleanupConflictFolderUntilPercent* parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CleanupConflictFolderUntilPercent
Specifies a percent value from 10 to 100.
The default value is 60.

After the DFS Replication service starts cleanup of the ConflictsAndDeleted folder, it continues to delete the oldest files until the folder size reaches this percent of the ConflictsAndDeleted quota.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CleanupStagingFolderAtPercent
Specifies a percent value from 80 to 100.
The default value is 90.

When the staging folder size reaches this percent of the staging folder quota, the DFS Replication service deletes the oldest files until the folder size falls below a set percent of the quota.
You can specify that percent value by using the *CleanupStagingFolderUntilPercent* parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CleanupStagingFolderUntilPercent
Specifies a percent value from 10 to 80.
The default value is 60.

After the DFS Replication service starts cleanup of the staging folder, it continues to delete the oldest files until the folder size reaches this percentage of the staging folder quota.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of replication member computers.
The cmdlet modifies membership settings for these member computers.
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet modifies settings for the current computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -DebugLogPath
Specifies a folder path for DFS Replication debug logs.
The default location for the logs is %SystemRoot%\Debug.
If you specify a custom location for logs by using this parameter, select a drive that DFS Replication does not use for replication.
Selecting a drive that DFS Replication does not use for replication minimizes the impact of logging on replication performance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugLogSeverity
Specifies a severity level for debug log entries.
The acceptable values for this parameter are:

- 1 - Write log header information only.
- 2 - Write errors and header information.
- 3 - Write warning, error, and header information.
- 4 - Write informational, warning, error, and header information.
- 5 - Write trace, informational, warning, error, and header information.

The default value on a DFS Replication computer is 4.
If you increase the severity, performance can suffer.
Use a higher severity level only for troubleshooting.
If you decrease the severity, performance increases slightly but you might lose information necessary to troubleshoot issues and lose root cause information.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDebugLog
Indicates whether to disable debug logging.
If you disable debug logging, performance increases slightly but you might lose information necessary to troubleshoot issues and lose root cause information.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumDebugLogFiles
Specifies the number of debug log files to keep.
The acceptable values for this parameter are: integers from zero (0) to 100,000.
By default, DFS Replication stores 1000 log files.
A larger value can degrade performance.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumDebugLogMessages
Specifies the number of messages to write in each debug log file.
The acceptable values for this parameter are: integers from 1000 to 4294967295.
The default value is 200,000.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RPCPort
Specifies a static TCP port for the DFS Replication service to listen on for the Remote Procedure Call (RPC) protocol.
The acceptable values for this parameter are: integers from 1024 to 65535.
By default, DFS Replication listens on a dynamic port.
Specify a value of zero (0) or $Null for DFS Replication to listen on a dynamic port.

Microsoft recommends a dynamic port.
You might need to specify a static port to accommodate a firewall.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnexpectedAutoRecovery
Indicates whether to set the value for the registry key named **StopReplicationAutoRecovery** to zero (0) or one (1).
A value of zero allows the server to automatically recover after it shuts down incorrectly or hardware fails.
Specify a value of $False to set this registry value to one (1).
The default value is zero.

When a server shuts down incorrectly and recovers automatically, the database must be validated.
Setting the value to one allows you to perform other recovery, backup, or troubleshooting options before resuming replication.

The recommended value for this parameter is $True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
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

### String

## OUTPUTS

### DfsrServiceConfiguration

## NOTES

## RELATED LINKS

[Get-DfsrServiceConfiguration](./Get-DfsrServiceConfiguration.md)

[Get-DfsrMember](./Get-DfsrMember.md)

[Set-DfsrMembership](./Set-DfsrMembership.md)


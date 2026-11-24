---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/debug-storagesubsystem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-StorageSubSystem
---

# Debug-StorageSubSystem

## SYNOPSIS
Finds problems with a storage subsystem and recommends solutions.

## SYNTAX

### ByFriendlyName (Default)
```
Debug-StorageSubSystem [-StorageSubSystemFriendlyName] <String[]> [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Debug-StorageSubSystem -StorageSubSystemUniqueId <String[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByName
```
Debug-StorageSubSystem -StorageSubSystemName <String[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### InputObject
```
Debug-StorageSubSystem -InputObject <CimInstance> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Debug-StorageSubSystem** cmdlet finds problems with a storage subsystem and recommends solutions.

## EXAMPLES

### Example 1: Debug the local storage subsystem
```
PS C:\>Get-StorageSubsystem | Debug-StorageSubSystem
```

This command gets the local storage subsystem and passes it to the **Debug-StorageSubsystem** cmdlet.
The current cmdlet generates a health report for the storage subsystem.

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
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystemFriendlyName
Specifies the friendly name of the Storage subsystem for which to gather storage diagnostics.
It may denote the Storage subsystem of the local computer (on which the cmdlet is run) or a remote Storage subsystem (standalone or cluster).

Selecting the local subsystem:


- On a standalone machine, no remote subsystems: All logs are gathered for that computer.

- On a standalone machine, remote subsystems registered: All logs are gathered for the standalone machine, including the client-side remoting calls.

- On a cluster node: All logs for that particular cluster node are gathered, even ones that belong in the cluster subsystem for that node only.
None of the other nodes are logged.



Selecting the cluster subsystem:


- All logs are gathered for each node in that cluster.
This includes and logs or tracing that may correspond to a node's local subsystem.



Selecting a remote subsystem:


- Tracing and logs are only gathered for the remote endpoint.
What logs and tracing are gathered depend on whether it is a cluster or a standalone machine (see above cases).

- Tracing and logs for the client-side operations (running on the management node) are not collected.
It is expected that if there is a failure, it is most likely in the remote subsystem.

In order to gather the client-side calls, you must also include the management node's local subsystem.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystemName
Specifies the name of the Storage subsystem for which to gather Storage diagnostics.
It may denote the Storage subsystem of the local computer (on which the cmdlet is run) or a remote Storage subsystem (standalone or cluster).

Selecting the local subsystem:


- On a standalone machine, no remote subsystems: All logs are gathered for that computer.

- On a standalone machine, remote subsystems registered: All logs are gathered for the standalone machine, including the client-side remoting calls.

- On a cluster node: All logs for that particular cluster node are gathered, even ones that belong in the cluster subsystem for that node only.
None of the other nodes are logged.



Selecting the cluster subsystem:


- All logs are gathered for each node in that cluster.
This includes and logs or tracing that may correspond to a node's local subsystem.



Selecting a remote subsystem:


- Tracing and logs are only gathered for the remote endpoint.
What logs and tracing are gathered depend on whether it is a cluster or a standalone machine (see above cases).

- Tracing and logs for the client-side operations (running on the management node) are not collected.
It is expected that if there is a failure, it is most likely in the remote subsystem.

In order to gather the client-side calls, you must also include the management node's local subsystem.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystemUniqueId
Specifies the unique ID of the Storage subsystem for which to gather Storage diagnostics.
It may denote the Storage subsystem of the local computer (on which the cmdlet is run) or a remote Storage subsystem (standalone or cluster).

Selecting the local subsystem:


- On a standalone machine, no remote subsystems: All logs are gathered for that computer.

- On a standalone machine, remote subsystems registered: All logs are gathered for the standalone machine, including the client-side remoting calls.

- On a cluster node: All logs for that particular cluster node are gathered, even ones that belong in the cluster subsystem for that node only.
None of the other nodes are logged.



Selecting the cluster subsystem:


- All logs are gathered for each node in that cluster.
This includes and logs or tracing that may correspond to a node's local subsystem.



Selecting a remote subsystem:


- Tracing and logs are only gathered for the remote endpoint.
What logs and tracing are gathered depend on whether it is a cluster or a standalone machine (see above cases).

- Tracing and logs for the client-side operations (running on the management node) are not collected.
It is expected that if there is a failure, it is most likely in the remote subsystem.

In order to gather the client-side calls, you must also include the management node's local subsystem.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases:

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageSubSystem](./Get-StorageSubsystem.md)

[Register-StorageSubsystem](./Register-StorageSubsystem.md)

[Set-StorageSubSystem](./Set-StorageSubsystem.md)

[Unregister-StorageSubsystem](./Unregister-StorageSubsystem.md)


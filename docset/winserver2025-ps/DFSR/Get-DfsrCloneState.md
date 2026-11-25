---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsrclonestate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrCloneState
---

# Get-DfsrCloneState

## SYNOPSIS
Gets the status of a database cloning operation.

## SYNTAX

```
Get-DfsrCloneState [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrCloneState** cmdlet gets the status of an ongoing cloning operation for a volume from the local computer.
The cmdlet returns the state of exporting or importing configuration XML file settings for a Distributed File System (DFS) Replication database or volume.

This cmdlet does not have any parameters and returns only state information.
You must run this cmdlet on the DFS Replication computer that performs the export or import.
Only one import or export can run at a time on a server.

The DFS Replication service can return the following cloning states:

- Ready. The DFS Replication service is ready to perform cloning. This is the status both before cloning starts and after cloning completes.
- Started DB Export. The DFS Replication service has begun the export process and is validating prerequisites.
- Started DB Import. The DFS Replication service has begun the import process and is validating prerequisites.
- Processing DB Export. The DFS Replication service is exporting the database.
- Processing DB Import. The DFS Replication service is importing the database.
- Resetting. The DFS Replication service is cancelling and rolling back the import or export.
- Shut down. The DFS Replication database is shut down due to a requested backup or restore operation.
- Shutting down. The DFS Replication database is shutting down because of a requested backup or restore operation, or because of a requested service shut down.

## EXAMPLES

### Example 1: Get the state of DFS Replication cloning
```
PS C:\> Get-DfsrCloneState
Ready
```

This command gets the state of DFS Replication cloning.
In this case the server is not currently cloning.
The cloning operation has not started or has finished.

### Example 2: Get the state during a cloning operation
```
The first command exports a cloned DFS Replication database and volume configuration settings from C:\DfsRClone.
PS C:\> Export-DfsrClone -Volume "C:" -Path "C:\DfsRClone" -Force

The second command returns the state that indicates that the DFSR service has begun the export process and is validating prerequisites.
PS C:\> Get-DfsrCloneState
Started DB Export

The third command returns the state that indicates that the DFS Replication service is exporting the database.
PS C:\> Get-DfsrCloneState
Processing DB Export

The fourth command returns the state that indicates that the cloning is complete and the DFS Replication service is ready to perform cloning.
PS C:\> Get-DfsrCloneState
Ready
```

This example exports a DFS Replication database clone and gets the status of the ongoing cloning operation.
The first command runs in one Windows PowerShell console, and the remaining commands run in a second Windows PowerShell console.
This is required because the **Export-DfsrClone** cmdlet does not return until the DFS Replication service completes the export or if you press Ctrl + C to exit the cmdlet.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### DfsrCloneState

## NOTES

## RELATED LINKS

[Import-DfsrClone](./Import-DfsrClone.md)

[Export-DfsrClone](./Export-DfsrClone.md)

[Reset-DfsrCloneState](./Reset-DfsrCloneState.md)


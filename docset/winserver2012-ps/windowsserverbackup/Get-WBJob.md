---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 08375C25-61AF-4928-B052-A9993DCACAD7
manager: dansimp
---

# Get-WBJob

## SYNOPSIS
Gets the current backup operation.

## SYNTAX

```
Get-WBJob [[-Previous] <UInt32>]
```

## DESCRIPTION
The **Get-WBJob** cmdlet gets the current backup operation (if one is running) or the previous backup or recovery operation.
A **WBJob** object contains the backup or recovery operation.

To start a backup, use the Start-WBBackup cmdlet.

To use Windows Server® 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get backup status
```
PS C:\>$Policy = Get-WBPolicy PS C:\>Start-WBBackup -Policy $Policy -Async PS C:\>$Job = Get-WBJob
```

This example gets the status of the currently running backup or recovery operation.

The first command gets a backup policy object that contains the backup policy for the current computer and stores this policy in the variable named **$Policy**.

The second command starts the backup job by using the policy in the variable named **$Policy**.
Because the command uses the **Async** parameter, the backup job does not display status messages as it runs.

The third command gets status information about the backup job and assigns it to the variable named **$Job**.
Because the previous command specified the **Async** parameter, you can use the Get-WBJob cmdlet to obtain this information.

### Example 2: Get the status of past backup or recovery jobs
```
PS C:\> $Jobs = Get-WBJob -Previous 10
```

This command gets the status of the last 10 backup or recovery jobs from the backup events in the event manager.
It then stores the status in the variable named **$Jobs**.

## PARAMETERS

### -Previous
Specifies the number of previous backup operations for which the server queries the event manager.

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

## INPUTS

### Previous
If you use the **Previous** parameter, the Get-WBJob cmdlet queries a **WBJob** object for previously run backups and recoveries.
If you do not use this parameter, the cmdlet returns a **WBJob** object that contains the currently running backup or recovery operation.

## OUTPUTS

### WBJob[]
The Get-WBJob cmdlet displays a **WBJob** object that contains the currently or previously running backup or recovery operation.

## NOTES

## RELATED LINKS

[Start-WBBackup](./Start-WBBackup.md)

[Stop-WBJob](./Stop-WBJob.md)


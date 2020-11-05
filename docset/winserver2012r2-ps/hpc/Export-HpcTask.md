---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Export-HpcTask
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Export-HpcTask

## SYNOPSIS
Exports the settings for a task to an XML file.

## SYNTAX

### task (Default)
```
Export-HpcTask -Task <HpcTask> -Path <String> [-Force] [-Scheduler <String[]>] [<CommonParameters>]
```

### id
```
Export-HpcTask -JobId <Int32> -TaskId <Int32> -Path <String> [-Force] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-HpcTask** cmdlet exports the settings for the specified task to a task XML file.
You can specify the task for which you want to export the settings by using the job identifier and task identifier for the task or by using an **HpcTask** object.
After you export the task XML file, you can then specify the task XML file in the *TaskFile* parameter of the Add-HpcTask cmdlet to add a new task to a job with the same settings as the exported task.

## EXAMPLES

### Example 1: Export a task
```
PS C:\>Export-HpcTask -JobId 1 -TaskId 1 -Path "C:\MyTasks\Task_1_1.xml"
```

This command exports the settings for the first task in the job with a job ID of 1 to a file at C:\MyTasks\Task_1_1.xml.

### Example 2: Get a task object and export its settings
```
PS C:\>Get-HpcTask -JobId 2 -TaskId 4 | Export-HpcTask -Path "C:\MyTasks\Task_2_4.xml"
```

This command gets an **HpcTask** object for the fourth task in the job with a job ID of 2, and then exports the settings for that task to a file at C:\MyTasks\Task_2_4.xml.

## PARAMETERS

### -Force
Replaces the task XML file if it already exists, without prompting the user.

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

### -JobId
Specifies the job identifier of the job that contains the task that you want to export.
If you specify the *JobID* parameter, you must also specify the *TaskId* parameter.
You can use the *JobId* and *TaskId* parameters together to specify the job you want to export, or you can use the *Task* parameter instead, but you cannot combine the *Task* parameter with the *JobId* or *TaskId* parameter.

```yaml
Type: Int32
Parameter Sets: id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies a name for the XML file to which you want to export the task, including the full or relative path to the file if the **Export-HpcTask** cmdlet should not save the file in the current directory.

This cmdlet creates any directories that do not already exist in that path.
If the file already exists, the cmdlet prompts you to confirm whether you want to overwrite the file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the task.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

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

### -Task
Specifies an **HpcTask** object that represents the task that you want to export.
Use the Get-HpcTask cmdlet to get an **HpcTask** object for a task.
You can use the *Task* parameter to specify the job you want to export, or you can use a combination of the *JobId* and *TaskId* parameters instead, but you cannot combine the *Task* parameter with the *JobId* or *TaskId* parameter.

```yaml
Type: HpcTask
Parameter Sets: task
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskId
Specifies the task identifier of the tasks that you want to export.
If you specify the *TaskId* parameter, you must also specify the *JobId* parameter.
You can use the *JobId* and *TaskId* parameters together to specify the job you want to export, or you can use the *Task* parameter instead, but you cannot combine the *Task* parameter with the *JobId* or *TaskId* parameter.

```yaml
Type: Int32
Parameter Sets: id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcTask

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-HpcTask](./Add-HpcTask.md)

[Get-HpcTask](./Get-HpcTask.md)

[Set-HpcTask](./Set-HpcTask.md)

[Stop-HpcTask](./Stop-HpcTask.md)

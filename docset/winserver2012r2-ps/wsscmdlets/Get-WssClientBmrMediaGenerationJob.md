---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssClientBmrMediaGenerationJob
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 217AB508-9EF0-417F-8342-26619569F4C1
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssClientBmrMediaGenerationJob

## SYNOPSIS
Gets the client full system restore media generation job status for a full system restore.

## SYNTAX

```
Get-WssClientBmrMediaGenerationJob [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssClientBmrMediaGenerationJob** cmdlet gets the client full system restore media generation job status.
A full system restore recovers the operating system from a backup, and is also called bare metal recovery (BMR).
The status includes: 

- Status.
The current status of the job.
- LastStage.
The last status of the job.
- Result.
The job run result.
- BootableMediaPath.
The path to the bootable media.

The status also checks if the Original Equipment Manufacturer (OEM) image exists, if the Assessment and Deployment Kit (ADK) is ready, if the restore image is ready, if the media is ready, and if the Windows Deployment Services (WDS) image is deployed.

## EXAMPLES

### Example 1: Get the media generation job status
```
PS C:\> Get-WssClientBmrMediaGenerationJob
```

This command gets the media generation job status.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.GenBmrJobExecutionInfo

## NOTES

## RELATED LINKS

[Start-WssClientBmrMediaGenerationJob](./Start-WssClientBmrMediaGenerationJob.md)

[Stop-WssClientBmrMediaGenerationJob](./Stop-WssClientBmrMediaGenerationJob.md)


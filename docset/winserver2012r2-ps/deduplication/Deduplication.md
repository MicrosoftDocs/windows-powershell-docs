---
Module Name: Deduplication
Module Guid: 1395ECA7-7EAF-4958-A114-FB8AB76B86CC
Download Help Link: http://go.microsoft.com/fwlink/?linkid=285740
Help Version: 4.0.3.0
Locale: en-US
title: Deduplication
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 72144cf9-f9f5-43b3-be84-5c959089c28f
---

# Deduplication Module
## Description
This reference provides cmdlet descriptions and syntax for all Windows Server Data Deduplication-specific cmdlets. 
It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

## Deduplication Cmdlets
### [Disable-DedupVolume](./Disable-DedupVolume.md)
Disables data deduplication activity on one or more volumes.

### [Enable-DedupVolume](./Enable-DedupVolume.md)
Enables data deduplication on one or more volumes.

### [Expand-DedupFile](./Expand-DedupFile.md)
Expands an optimized file into its original location.

### [Get-DedupJob](./Get-DedupJob.md)
Returns status and information for currently running or queued deduplication jobs.

### [Get-DedupMetadata](./Get-DedupMetadata.md)
Returns a DeduplicationMetadata object for every volume that has data deduplication metadata.

### [Get-DedupSchedule](./Get-DedupSchedule.md)
Returns the DeduplicationJobSchedule objects defined on the system.

### [Get-DedupStatus](./Get-DedupStatus.md)
Returns a Deduplication status object for every volume that has data deduplication metadata.

### [Get-DedupVolume](./Get-DedupVolume.md)
Returns a DeduplicationVolume object for each volume that has data deduplication metadata.

### [Measure-DedupFileMetadata](./Measure-DedupFileMetadata.md)
Measures potential disk space on a volume.

### [New-DedupSchedule](./New-DedupSchedule.md)
Creates a data deduplication schedule.

### [Remove-DedupSchedule](./Remove-DedupSchedule.md)
Deletes the specified DeduplicationSchedule object.

### [Set-DedupSchedule](./Set-DedupSchedule.md)
Changes configuration settings for data deduplication schedules.

### [Set-DedupVolume](./Set-DedupVolume.md)
Changes data deduplication settings on one or more volumes.

### [Start-DedupJob](./Start-DedupJob.md)
Starts a data deduplication job.

### [Stop-DedupJob](./Stop-DedupJob.md)
Cancels one or more specified data deduplication jobs.

### [Update-DedupStatus](./Update-DedupStatus.md)
Scans one or more specified volumes to compute fresh data deduplication savings information and returns a DeduplicationStatus object.


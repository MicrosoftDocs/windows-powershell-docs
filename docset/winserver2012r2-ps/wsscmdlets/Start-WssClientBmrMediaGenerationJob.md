---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Start-WssClientBmrMediaGenerationJob
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: F848EDB3-0087-4F62-A331-7B06DC6605E5
ms.author: kenwith
ms.reviewer: brianlic
---

# Start-WssClientBmrMediaGenerationJob

## SYNOPSIS
Starts the client full system restore media generation job.

## SYNTAX

```
Start-WssClientBmrMediaGenerationJob -JobType <GenBmrJobType> [-UsbDriveGuid <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WssClientBmrMediaGenerationJob** cmdlet starts the client full system restore media generation job.
A full system restore recovers the operating system from backup, and is also called bare metal recovery (BMR).

## EXAMPLES

### Example 1: Start a media generation job for bare metal recovery
```
PS C:\> Start-ClientBmrMediaGenerationJob -JobType 1 -UsbDriveGuid "{77FC2704-25CC-48CC-B32F-25F9EBB19338}"
```

This command starts a bare metal recovery media generation job by using a USB drive.

## PARAMETERS

### -JobType
Specifies the job type.
The acceptable values for this parameter are:

- 0  Client Restore Service
- 1  USB

```yaml
Type: GenBmrJobType
Parameter Sets: (All)
Aliases: 
Accepted values: Wds, ServerUsb

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsbDriveGuid
Specifies the job type.
The acceptable values for this parameter are:

- 0  Client Restore Service
- 1  USB

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssClientBmrMediaGenerationJob](./Get-WssClientBmrMediaGenerationJob.md)

[Stop-WssClientBmrMediaGenerationJob](./Stop-WssClientBmrMediaGenerationJob.md)


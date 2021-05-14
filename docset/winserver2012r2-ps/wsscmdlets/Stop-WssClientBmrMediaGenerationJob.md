---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/stop-wssclientbmrmediagenerationjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-WssClientBmrMediaGenerationJob
---

# Stop-WssClientBmrMediaGenerationJob

## SYNOPSIS
Stops a client full system restore media generation job.

## SYNTAX

```
Stop-WssClientBmrMediaGenerationJob [<CommonParameters>]
```

## DESCRIPTION
The **Stop-WssClientBmrMediaGenerationJob** cmdlet stops a client full system restore media generation job.
A full system restore recovers the operating system from a backup, and is also called bare metal recovery (BMR).

## EXAMPLES

### Example 1: Stop a media generation job for bare metal recovery
```
PS C:\> Stop-WssClientBmrMediaGenerationJob
```

This command stops a bare metal recovery media generation job.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssClientBmrMediaGenerationJob](./Get-WssClientBmrMediaGenerationJob.md)

[Start-WssClientBmrMediaGenerationJob](./Start-WssClientBmrMediaGenerationJob.md)


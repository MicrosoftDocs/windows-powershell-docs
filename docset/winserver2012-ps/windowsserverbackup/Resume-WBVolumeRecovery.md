---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: F4AF6DD5-285C-41E2-9B4A-CC5AEFF0CDE6
manager: dansimp
---

# Resume-WBVolumeRecovery

## SYNOPSIS
Resumes a volume recovery operation from a removable device and specific media.

## SYNTAX

```
Resume-WBVolumeRecovery
```

## DESCRIPTION
The **Resume-WBVolumeRecovery** cmdlet resumes a volume recovery operation performed from a removable device and specific media.
If the requested media is not inserted, the cmdlet returns an error with a description of the requested media.
Otherwise, the cmdlet returns confirmation that the recovery operation resumed.

## EXAMPLES

### Example 1: Resume a volume recovery operation
```
PS C:\> Resume-WBVolumeRecovery
```

This command resumes the volume recovery operation.

## PARAMETERS

## INPUTS

## OUTPUTS

### System.String, System.Exception
If the requested media is not inserted, the cmdlet returns an error with the description of the requested media.
Otherwise, the recovery operation resumes and the cmdlet returns a confirmation message.

## NOTES

## RELATED LINKS

[Start-WBVolumeRecovery](./Start-WBVolumeRecovery.md)


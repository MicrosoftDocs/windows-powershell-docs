---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 5FBD4A20-C137-478D-825D-8202E4492D5B
manager: dansimp
---

# Resume-WBBackup

## SYNOPSIS
Resumes a backup operation to a removable device after you add media to the device.

## SYNTAX

```
Resume-WBBackup [-ForceFormat]
```

## DESCRIPTION
The **Resume-WBBackup** cmdlet resumes a backup operation when you are backing up to a removable device and must add new media.

If the media that you add contain data and you must format the media, call this cmdlet with the **ForceFormat** parameter.
If the device does not contain media, the cmdlet returns with an error message that describes the missing media.
If the device contains media, the cmdlet returns confirmation that the backup has resumed.

## EXAMPLES

### Example 1: Resume a backup
```
PS C:\> Resume-WBBackup
```

This command resumes a backup operation.

## PARAMETERS

### -ForceFormat
Indicates that the media contain data and need formatting.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### ForceFormat
If the media contain data and need formatting, call this cmdlet with the **ForceFormat** parameter.

## OUTPUTS

### System.String, System.Exception
If the removable device does not contain the requested media, the cmdlet returns with an error message that describes the missing media.
If the device contains media, the cmdlet returns confirmation that the backup has resumed.

## NOTES

## RELATED LINKS




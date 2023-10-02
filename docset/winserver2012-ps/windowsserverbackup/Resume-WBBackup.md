---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/resume-wbbackup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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




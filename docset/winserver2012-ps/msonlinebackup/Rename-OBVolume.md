---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: E417C2FF-13CC-4290-A833-9EB73EC4DAF9
---

# Rename-OBVolume

## SYNOPSIS
Maps a backed up volume to its new name after the operating system has been reinstalled on the backed up server.

## SYNTAX

```
Rename-OBVolume [-OldVolumeName] <String> [-NewVolumeName] <String>
```

## DESCRIPTION
The Rename-OBVolume cmdlet maps a backed up volume to its new name after the operating system has been reinstalled on the backed up server.
. This cmdlet is useful in the scenario where the operating system is reinstalled and as a result the volume GUID of a backed up volume is changed.
After this cmdlet has been run the backup policy of OldVolumeName would be applied to NewVolumeName.

Note: OldVolumeName and NewVolumeName can be same if the volume GUID has changed but the volume name has not changed.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Rename-OBVolume D: E:
```

This example maps E: to an older volume D:.
Policy details such as files to included/exclude in backup for older volume D: would now be applied to E:

## PARAMETERS

### -NewVolumeName
Identifies the name of the new volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OldVolumeName
Identifies the name of the old volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### 
None

## OUTPUTS

### 
Microsoft.Internal.CloudBackup.Commands.OBVolume

## NOTES

## RELATED LINKS


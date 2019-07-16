---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: DB178BEF-D267-4546-9A2F-138E6F48A960
manager: dansimp
---

# Add-WBVolume

## SYNOPSIS
Adds the list of source volumes to the backup policy.

## SYNTAX

```
Add-WBVolume [-Policy] <WBPolicy> [-Volume] <WBVolume[]>
```

## DESCRIPTION
The **Add-WBVolume** cmdlet adds a list of source volumes to a **WBPolicy** object.

To use this and any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Add a list of volumes to a backup policy
```
PS C:\>$Volumes = Get-WBVolume PS C:\>$Policy = Get-WBPolicy PS C:\> Add-WBVolume -Policy $Policy -Volume $Volumes
```

This example adds a list of volumes for backup to the **WBPolicy** object.

The first command stores the output of the Get-WBVolume cmdlet in the variable named **$Volumes**.

The second command calls the Get-WBPolicy cmdlet and assigns the result to the **$Policy** variable.

The third command adds the volumes in the **$Volumes** variable to the backup policy.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Volume
Specifies an array of volumes to add to the **WBPolicy** object.

```yaml
Type: WBVolume[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### WBVolume [], WBPolicy
The **Add-WBVolume** cmdlet accepts **WBVolume** objects, which contain a new list of source volumes for the backup, and **WBPolicy** objects as input.

## OUTPUTS

### WBVolume[]
The **Add-WBVolume** cmdlet outputs the list of **WBVolume** objects in the **WBPolicy** object, including the **WBVolume** objects that the cmdlet just added.

## NOTES
* The **WBPolicy** object must be in edit mode. To put the **WBPolicy** object in edit mode for a policy that you set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the **Editable** parameter. The New-WBPolicy cmdlet creates a new **WBPolicy** object that is already in edit mode.

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBVolume](./Get-WBVolume.md)

[Remove-WBVolume](./Remove-WBVolume.md)


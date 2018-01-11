---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 1D5EE754-8135-453C-B6B7-4E0C1F0B35DF
---

# New-OBRecoverableItem

## SYNOPSIS
Creates a new OBRecoverableItem for the given path.

## SYNTAX

```
New-OBRecoverableItem [-OBRecoverableItem] <CBRecoverableItem> [-RelativePath] <String> [-IsDir] <Boolean>
```

## DESCRIPTION
The **New-OBRecoverableItem** cmdlet creates a new OBRecoverable item with a given relative path.
This file path would be used to recover the file item from a recovery point.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $sources = Get-OBRecoverableSource
$rp = Get-OBRecoverableItem $sources[0]
$new_item1 = New-OBRecoverableItem $rp[0] "resources\folder" $TRUE
$new_item2 = New-OBRecoverableItem $rp[0] "resources\folder\file.txt" $FALSE
Start-OBRecovery @($new_item1, $new_item2)
```

This example creates a new recovery item.

## PARAMETERS

### -IsDir
Specify if the relative path is a directory through the use of the Boolean value TRUE or a file by specifying FALSE.
This parameter is mandatory.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OBRecoverableItem
This is the point in time to which the relative path will be appended to create the new recoverable item.

```yaml
Type: CBRecoverableItem
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RelativePath
This is the relative path which would be appended to the given recoverable item to create the new recoverable item.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBRecoverableItem

## NOTES

## RELATED LINKS

[Get-OBRecoverableItem](./Get-OBRecoverableItem.md)

[New-OBRecoveryOption](./New-OBRecoveryOption.md)

[Start-OBRecovery](./Start-OBRecovery.md)


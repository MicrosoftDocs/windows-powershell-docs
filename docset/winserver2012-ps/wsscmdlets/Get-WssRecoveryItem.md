---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: D6C1F900-9AB6-4864-9DDC-82A8670D5C5B
manager: dansimp
---

# Get-WssRecoveryItem

## SYNOPSIS
Gets child recovery items from a parent recovery item.

## SYNTAX

```
Get-WssRecoveryItem [-Parent] <RecoveryItem>
```

## DESCRIPTION
The **Get-WssRecoveryItem** cmdlet gets child recovery items from a parent recovery item. 
When you restore a file or folder, this cmdlet helps you locate the file or folder to restore by browsing from the root folder to the child folders, until you locate the missing folder.

## EXAMPLES

### Example 1: Get child recovery items
```
PS C:\> $ContosoRecOptions05Child = Get-WssRecoveryItem -Parent $ContosoRecOptions05Parent
```

This command gets child recovery options from the parent node that is stored in the variable named $ContosoRecOptions05Parent and stores those options in the variable named $ContosoRecOptions05Child.

## PARAMETERS

### -Parent
Specifies the parent recovery item.

```yaml
Type: RecoveryItem
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-WssRecoveryOption](./New-WssRecoveryOption.md)


---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssrecoveryitem?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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


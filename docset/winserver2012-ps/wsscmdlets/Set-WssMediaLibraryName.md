---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 9B539128-39E2-479D-9255-916BE6CE0392
manager: dansimp
---

# Set-WssMediaLibraryName

## SYNOPSIS
Changes the name of the Media Library.

## SYNTAX

```
Set-WssMediaLibraryName [-MediaLibraryName] <String>
```

## DESCRIPTION
The **Set-WssMediaLibraryName** cmdlet changes the name of the Media Library for the current server.
You can use the Get-WssMediaLibraryName cmdlet to see the Media Library name.

## EXAMPLES

### Example 1: Rename a Media Library
```
PS C:\> Set-WssMediaLibraryName -MediaLibraryName "Accounting Library"
```

This command gives the Media Library the name Accounting Library.

## PARAMETERS

### -MediaLibraryName
Specifies a new name for the Media Library shared by the server.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaLibraryName](./Get-WssMediaLibraryName.md)


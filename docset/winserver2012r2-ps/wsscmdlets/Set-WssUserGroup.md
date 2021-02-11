---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssUserGroup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: A861A82A-FF48-4D16-86B7-0FBDD4275A2B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssUserGroup

## SYNOPSIS
Modifies properties of a user group.

## SYNTAX

```
Set-WssUserGroup -GroupName <String> [-Description <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssUserGroup** cmdlet modifies properties of a Windows Server Essentials user group.

## EXAMPLES

### Example 1: Modify a description for a group
```
PS C:\> Set-WssUserGroup -GroupName "HRGroup" -Description "User group for the HR"
```

This command modifies the description for the group named HRGroup.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Description
Specifies a description.
The cmdlet modifies the user group to have the description that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
Specifies the name of a user group.
The cmdlet modifies the user group that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssUserGroup](./Add-WssUserGroup.md)

[Get-WssUserGroup](./Get-WssUserGroup.md)

[Remove-WssUserGroup](./Remove-WssUserGroup.md)


---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssMsoGroupAssignment
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E5AE58D3-93CC-42A1-8D30-53F87A2B4EE2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssMsoGroupAssignment

## SYNOPSIS
Assigns a security group to a user group.

## SYNTAX

```
Set-WssMsoGroupAssignment [-WssGroupName] <String> [-MsoId] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMsoGroupAssignment** cmdlet assigns a aad_1 security group to a Windows Server Essentials user group.

## EXAMPLES

### Example 1: Assign a security group
```
PS C:\> Set-WssMSOAssignedGroup -WssGroupName "Admins" -MsoId "d77e9419-2e1f-4080-ae7c-9b97c6caa681"
```

This command assigns the specified security group to the user group named Admins.

### 1:
```
PS C:\>
```

## PARAMETERS

### -MsoId
Specifies an ID for a security group.
The cmdlet assign the security group that you specify to a Windows Server Essentials user group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WssGroupName
Specifies the name of a Windows Server Essentials user group.
The cmdlet assigns a security group to the gets the user group that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
WssGroupName
Type: System.String
Description: local network account name of group

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WssMsoGroupAssignment](./Remove-WssMsoGroupAssignment.md)

[Set-WssMsoUserAssignment](./Set-WssMsoUserAssignment.md)


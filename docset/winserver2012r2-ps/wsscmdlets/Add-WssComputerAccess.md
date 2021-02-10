---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Add-WssComputerAccess
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: CC660DCC-301B-434F-AB10-BD4203A38FC7
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-WssComputerAccess

## SYNOPSIS
Creates a relationship between a user and a computer for Remote Web Access.

## SYNTAX

```
Add-WssComputerAccess -ComputerName <String> [-UserName <String>] [-GroupName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssComputerAccess** cmdlet creates a relationship between a user account and a computer to use for Remote Web Access.
You can use the Remove-WssComputerAccess cmdlet to delete an access relationship.

## EXAMPLES

### Example 1: Add computer access for a user
```
PS C:\> Add-WssComputerAccess -ComputerName "Workstation033" -UserName "SarahJones"
```

This command creates a relationship between the user SarahJones and the computer named Workstation033.
The user can now use Remote Web Access to connect to this computer.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

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

### -GroupName
Specifies the name of a group.

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

### -UserName
Specifies the user name of an account.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WssComputerAccess](./Remove-WssComputerAccess.md)


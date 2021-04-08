---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wsscomputeraccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WssComputerAccess
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


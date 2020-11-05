---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssMsoGroup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3B8EE9F4-DE35-424A-ACF7-58037935AFAC
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssMsoGroup

## SYNOPSIS
Gets security groups.

## SYNTAX

```
Get-WssMsoGroup [[-MsoId] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoGroup** cmdlet gets aad_1 security groups.
Specify an ID to get a particular security group.
The cmdlet gets security groups whether or not they have an assignment to a user group.

## EXAMPLES

### Example 1: Get all security groups
```
PS C:\> Get-WssMSOGroup
LocalGroupName : Admins

Description    :

IdentityType   : SecurityGroup

ObjectId       : 70769c52-b6e2-4ef6-8369-3c2a0208da68

PrincipleName  :

DisplayName    : Administrators


LocalGroupName : All Employees

Description    :

IdentityType   : SecurityGroup

ObjectId       : d77e9419-2e1f-4080-ae7c-9b97c6caa681

PrincipleName  :

DisplayName    : All Employees


LocalGroupName :

Description    :

IdentityType   : SecurityGroup

ObjectId       : 77378d14-80ab-48fe-a2d4-e610b2c7eef6

PrincipleName  :

DisplayName    : Other Admins
```

This command gets all the security groups.

### Example 2: Get a specific security group
```
PS C:\> Get-WssMsoGroup -MsoId "70769c52-b6e2-4ef6-8369-3c2a0208da68"
LocalGroupName :

Description    :

IdentityType   : SecurityGroup

ObjectId       : 70769c52-b6e2-4ef6-8369-3c2a0208da68

PrincipleName  :

DisplayName    : Other Admins
```

This command gets the security group that has the specified ID.

## PARAMETERS

### -MsoId
Specifies an ID for a security group.
The cmdlet gets the security group that has the ID that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

[Add-WssMsoGroup](./Add-WssMsoGroup.md)

[Remove-WssMsoGroup](./Remove-WssMsoGroup.md)


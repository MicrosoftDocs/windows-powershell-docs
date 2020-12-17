---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssMsoAssignedGroup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: BC135D76-DB8C-4BC1-924E-C6162B466F89
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssMsoAssignedGroup

## SYNOPSIS
Gets a security group assigned to a user group.

## SYNTAX

```
Get-WssMsoAssignedGroup [[-WssGroupName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoAssignedGroup** cmdlet gets a aad_1 security group that is assigned to a Windows Server Essentials user group.
If you do not specify a user group, the cmdlet gets all the aad_2 security groups.
To get security groups that are not assigned to a user group, use the Get-WssMsoGroup cmdlet.

## EXAMPLES

### Example 1: Get all security groups
```
PS C:\> Get-WssMsoAssignedGroup
LocalGroupName : All Employee
Description    :
IdentityType   : SecurityGroup
ObjectId       : d77e9419-2e1f-4080-ae7c-9b97c6caa681
PrincipleName  :
DisplayName    : All Employees

LocalGroupName : Admins
Description    :
IdentityType   : SecurityGroup
ObjectId       : 77378d14-80ab-48fe-a2d4-e610b2c7eef6
PrincipleName  :
DisplayName    : Administrators
```

This command gets all the security groups.

### Example 2: Get a security group by name
```
PS C:\> Get-WssMsoAssignedGroup -WssGroupName "Admins"
LocalGroupName : Admins
Description    :
IdentityType   : SecurityGroup
ObjectId       : 77378d14-80ab-48fe-a2d4-e610b2c7eef6
PrincipleName  :
DisplayName    : Administrators
```

This command gets the security group assigned to the user group named Admins.

### 1:
```
PS C:\>
```

## PARAMETERS

### -WssGroupName
Specifies the name of a Windows Server Essentials user group.
The cmdlet gets the security group that is assigned to the user group that you specify.

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

### MSOSecurityGroup[]

## NOTES

## RELATED LINKS

[Add-WssMsoGroup](./Add-WssMsoGroup.md)

[Add-WssUserGroup](./Add-WssUserGroup.md)

[Get-WssMsoGroup](./Get-WssMsoGroup.md)


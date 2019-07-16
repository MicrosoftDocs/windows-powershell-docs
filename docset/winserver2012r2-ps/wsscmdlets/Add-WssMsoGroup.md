---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Add-WssMsoGroup
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 13C3E28E-563A-415A-A576-893541B86CBD
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Add-WssMsoGroup

## SYNOPSIS
Adds a security group and assigns it to a user group.

## SYNTAX

```
Add-WssMsoGroup [-WssGroupName] <String> [[-MsoGroupName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssMsoGroup** cmdlet adds a aad_1 security group, and assigns that group to a Windows Server Essentials user group.

## EXAMPLES

### Example 1: Create a security group
```
PS C:\> Add-WssMSOGroup - WssGroupName "Local Network Admins" -MsoGroupName "Network Admins"
```

This command creates a security group named Network Admins and associates it to the local network user group named Local Network Admins.

## PARAMETERS

### -MsoGroupName
Specifies a name for the security group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WssGroupName
Specifies the name of a user group.
The cmdlet assigns the security group to the user group that you specify.
If you do not specify a name for the security group by using the **MsoGroupName** parameter, the cmdlet uses the value that you specify as the name for the security group.

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
Description: local network account name of user group

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMsoGroup](./Get-WssMsoGroup.md)

[Remove-WssMsoGroup](./Remove-WssMsoGroup.md)


---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Add-WssUserGroup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 66D04608-F0DE-4358-8F33-2489584E6BC7
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-WssUserGroup

## SYNOPSIS
Adds a user group to the dashboard.

## SYNTAX

```
Add-WssUserGroup -Name <String> [-Description <String>] [-AllowRemoteAccess] [-AllowVpnAccess]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssUserGroup** cmdlet adds a user group to the Windows Server Essentials dashboard.

## EXAMPLES

### Example 1: Add user group
```
PS C:\> Add-WssUserGroup -Name "Support" -Description "Customer Support Team"
```

This command adds a user group.

## PARAMETERS

### -AllowRemoteAccess
Indicates that members of the group can access the Remote Web Access website.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowVpnAccess
Indicates that members of the group can access the VPN server.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description.
The cmdlet assigns the user group the description that you specify.

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

### -Name
Specifies a name.
The cmdlet uses this name for the user group.

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

[Get-WssUserGroup](./Get-WssUserGroup.md)

[Remove-WssUserGroup](./Remove-WssUserGroup.md)

[Set-WssUserGroup](./Set-WssUserGroup.md)


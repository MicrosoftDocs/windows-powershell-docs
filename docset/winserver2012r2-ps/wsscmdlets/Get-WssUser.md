---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssUser
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B54B8194-0A30-4705-BB5F-57F413DEBD08
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-WssUser

## SYNOPSIS
Retrieves a user account by name or security identifier.

## SYNTAX

### AllParamSet (Default)
```
Get-WssUser [<CommonParameters>]
```

### ByNameParamSet
```
Get-WssUser [-Name] <String> [<CommonParameters>]
```

### BySidParamSet
```
Get-WssUser [-Sid] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssUser** cmdlet retrieves a sbs_sbs8_2 server user account.
To retrieve a user account by name, specify the login name.
To retrieve a user account by security identifier, specify the SID.
To retrieve all user accounts, use the cmdlet without arguments.

## EXAMPLES

### Example 1: Retrieve a user account by name
```
PS C:\> Get-WSSUser -Name "SarahJones"
```

This command retrieves a user account by name.

## PARAMETERS

### -Name
Specifies the logon name of a user.

```yaml
Type: String
Parameter Sets: ByNameParamSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sid
Specifies the security identifier of a user.

```yaml
Type: String
Parameter Sets: BySidParamSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Users.User
This cmdlet generates the server user object with the specified properties.

## NOTES

## RELATED LINKS

[Add-WssUser](./Add-WssUser.md)

[Remove-WssUser](./Remove-WssUser.md)


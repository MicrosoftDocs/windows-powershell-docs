---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssMsoUserLicense
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E1446E19-F80B-4E35-A034-EF9924C687D2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssMsoUserLicense

## SYNOPSIS
Assigns licenses to an account in aad_2.

## SYNTAX

```
Set-WssMsoUserLicense [-WssUserName] <String> [[-License] <MSOLicense[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMsoUserLicense** cmdlet assigns licenses to an online service account in aad_1.

## EXAMPLES

### Example 1: Store a license for a user
```
PS C:\> $Subscribe = Get-WssMsoSubscription
PS C:\> Set-WssMSOUserLicense -WssUserName "EvanNarvaez" -License $Subscribe.MSOLicenseSuite[0].MSOLicense
```

The first command uses the Get-WssMsoSubscription cmdlet to get subscription information, and then stores it in the **$Subscribe** variable.

The second command assigns a license, contained in the object stored in the **$Subscribe** variable, to the account named EvanNarvaez.
The command uses standard array notation to access the first member of the **MSOLicenseSuite** array, and refer to the associated **MSOLicense** object.

## PARAMETERS

### -License
Specifies an array of licenses as **MSOLicense** objects.
The cmdlet assigns the licenses that you specify to a user account.
To obtain **MSOLicense** objects, use the Get-WssMsoSubscription cmdlet to get subscription information.
Subscription information contains the **MSOLicenseSuite** array that refers to **MSOLicense** objects.

```yaml
Type: MSOLicense[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WssUserName
Specifies the name of the user account to which you want the licenses assigned.

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
WssUserName
Type: System.String
Description: local network account name of user

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMsoSubscription](./Get-WssMsoSubscription.md)


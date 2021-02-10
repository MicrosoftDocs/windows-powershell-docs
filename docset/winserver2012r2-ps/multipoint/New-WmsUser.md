---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: New-WmsUser
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 33DAEC0D-DC28-48F8-84B7-E1F8BAC16B6C
ms.reviewer:
ms.author: v-kaunu
---

# New-WmsUser

## SYNOPSIS
Change a Windows MultiPoint Server user account.

## SYNTAX

```
New-WmsUser [-Name] <String> [-UserName <String>] [-Password <String>] -UserType <UserType>
 [-Description <String>] [-TimeoutInSecond <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Set-WmsUser cmdlet updates a local user on the current Windows MultiPoint Server system.

## EXAMPLES

### Example
```
PS C:\> Set-WmsUser -Description RABlAHMAYwByAGkAcAB0AGkAbwBuAA== -Name Student1 -Password UABAAHMAcwB3ADAAcgBkAA== -UserName VQBzAGUAcgAgAGYAdQBsAGwAbgBhAG0AZQA= -UserType Standard
No output.
```

This command updates a user account with Description "Description", Name as "Student1", Password as "P@ssw0rd" and Username as "User fullname".

### 1:
```
PS C:\>
```

## PARAMETERS

### -Description
Description of the user account to be modified.

 This parameter is BASE64 encoded.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name


```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Password
The password of the user account to be updated. 

 This parameter is BASE64 encoded.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
The full name of the user account to be updated. 

 This parameter is BASE64 encoded.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UserType
The access level of the user account to be modified.
This can be standard, administrator, or if the local system is a MultiPoint Server, it can be a Multipoint Dashboard user.

```yaml
Type: UserType
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS


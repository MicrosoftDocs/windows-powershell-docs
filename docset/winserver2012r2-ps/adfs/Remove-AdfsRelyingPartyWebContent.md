---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Remove-AdfsRelyingPartyWebContent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: BDA9D85C-F15D-4584-B313-96C7B6BF08BF
---

# Remove-AdfsRelyingPartyWebContent

## SYNOPSIS
Removes a relying party web content object.

## SYNTAX

### IdentifierName (Default)
```
Remove-AdfsRelyingPartyWebContent [[-Locale] <CultureInfo>] -Name <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IdentifierObject
```
Remove-AdfsRelyingPartyWebContent [-TargetWebContent] <AdfsRelyingPartyWebContent> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsRelyingPartyWebContent** cmdlet removes a relying party web content object.
Specify a relying party web content object by using a name and locale, or use the Get-AdfsRelyingPartyWebContent cmdlet.
If you do not specify a locale, the cmdlet uses the invariant locale.

## EXAMPLES

### Example 1: Remove the web content object for the invariant locale
```
PS C:\> Remove-AdfsRelyingPartyWebContent -Name "RelyingParty01"
```

This command removes the web content object for the relying party named RelyingParty01 for the invariant locale.

### Example 2: Remove the web content object for a specified locale
```
PS C:\> Remove-AdfsRelyingPartyWebContent -Locale en-us -Name "RelyingParty01"
```

This command removes the web content object for the relying party named RelyingParty01 for the specified locale.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Locale
Specifies a locale.
The cmdlet removes relying party web content for the locale that you specify.
If you do not specify a locale, the cmdlet removes relying party web content for the invariant locale.

```yaml
Type: CultureInfo
Parameter Sets: IdentifierName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name.
The cmdlet removes the web content for the relying party that you specify by name.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetWebContent
Specifies a relying party web content object.
The cmdlet removes the object that you specify.
To obtain a relying party web content object, use the Get-AdfsRelyingPartyWebContent cmdlet.

```yaml
Type: AdfsRelyingPartyWebContent
Parameter Sets: IdentifierObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AdfsRelyingPartyWebContent](./Get-AdfsRelyingPartyWebContent.md)

[Set-AdfsRelyingPartyWebContent](./Set-AdfsRelyingPartyWebContent.md)


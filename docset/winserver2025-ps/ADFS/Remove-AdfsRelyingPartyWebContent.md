---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsrelyingpartywebcontent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsRelyingPartyWebContent
---

# Remove-AdfsRelyingPartyWebContent

## SYNOPSIS
Removes a relying party web content object.

## SYNTAX

### IdentifierName (Default)
```
Remove-AdfsRelyingPartyWebContent [[-Locale] <CultureInfo>] -TargetRelyingPartyName <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Remove-AdfsRelyingPartyWebContent [-TargetRelyingPartyWebContent] <AdfsRelyingPartyWebContent> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsRelyingPartyWebContent** cmdlet removes a relying party web content object.
Specify a relying party web content object by using a name and locale, or use the **Get-AdfsRelyingPartyWebContent** cmdlet.
If you do not specify a locale, the cmdlet uses the invariant locale.

## EXAMPLES

### Example 1: Remove the web content object for the invariant locale
```
PS C:\> Remove-AdfsRelyingPartyWebContent -TargetRelyingPartyName "RelyingParty01"
```

This command removes the web content object for the relying party named RelyingParty01 for the invariant locale.

### Example 2: Remove the web content object for a specified locale
```
PS C:\> Remove-AdfsRelyingPartyWebContent -Locale en-us -TargetRelyingPartyName "RelyingParty01"
```

This command removes the web content object for the relying party named RelyingParty01 for the specified locale.

## PARAMETERS

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

### -TargetRelyingPartyName
Specifies the name of the relying party from which to delete web content.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetRelyingPartyWebContent
Specifies the web content to remove from the relying party.

```yaml
Type: AdfsRelyingPartyWebContent
Parameter Sets: IdentifierObject
Aliases: TargetWebContent

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AdfsRelyingPartyWebContent](./Get-AdfsRelyingPartyWebContent.md)

[Set-AdfsRelyingPartyWebContent](./Set-AdfsRelyingPartyWebContent.md)


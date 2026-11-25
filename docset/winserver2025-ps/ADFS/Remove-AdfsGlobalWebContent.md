---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsglobalwebcontent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsGlobalWebContent
---

# Remove-AdfsGlobalWebContent

## SYNOPSIS
Removes a global web content object.

## SYNTAX

### IdentifierName (Default)
```
Remove-AdfsGlobalWebContent [[-Locale] <CultureInfo>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Remove-AdfsGlobalWebContent [-TargetWebContent] <AdfsGlobalWebContent> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsGlobalWebContent** cmdlet removes a global web content object that corresponds to a locale.
If you do not specify the *Locale* parameter, the cmdlet removes the global web content object of the invariant locale.
Active Directory Federation Services (AD FS) reverts to its default values when you remove all the global web content objects.

## EXAMPLES

### Example 1: Remove the global web content for the invariant locale
```
PS C:\> Remove-AdfsGlobalWebContent
```

This command removes the global web content object that corresponds to the invariant locale.

### Example 2: Remove the global web content for a locale
```
PS C:\> Remove-AdfsGlobalWebContent -Locale en-us
```

This command removes the global web content object that corresponds to en-us locale.

## PARAMETERS

### -Locale
Specifies a locale.
The cmdlet removes the global web content that corresponds to the locale that you specify.

```yaml
Type: CultureInfo
Parameter Sets: IdentifierName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetWebContent
Specifies the **AdfsGlobalWebContent** object to remove.
To obtain an **AdfsGlobalWebContent** object, use the **Get-AdfsGlobalWebContent** cmdlet.

```yaml
Type: AdfsGlobalWebContent
Parameter Sets: IdentifierObject
Aliases:

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

[Get-AdfsGlobalWebContent](./Get-AdfsGlobalWebContent.md)

[Set-AdfsGlobalWebContent](./Set-AdfsGlobalWebContent.md)

[Remove-AdfsGlobalWebContent](./Remove-AdfsGlobalWebContent.md)


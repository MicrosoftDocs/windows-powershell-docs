---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wssremotewebaccesslink?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WssRemoteWebAccessLink
---

# Add-WssRemoteWebAccessLink

## SYNOPSIS
Adds a link to the home page of a Remote Web Access website.

## SYNTAX

```
Add-WssRemoteWebAccessLink -Text <String> -Url <Uri> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssRemoteWebAccessLink** cmdlet adds a link to the home page of a Remote Web Access website.

To remove a link from the home page of a Remote Web Access website, use the **Remove-WssRemoteWebAccessLink** cmdlet.

## EXAMPLES

### Example 1: Add a link to a home page
```
PS C:\> Add-WssRemoteWebAccessLink -Text "Link1" -Url "http://Contoso.com/About-Contoso-Page.html"
```

This command adds a link to the home page for a Remote Web Access website.

## PARAMETERS

### -Text
Specifies a text string for a link that displays on the home page.

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

### -Url
Specifies a web address for the link, as an absolute URI.

```yaml
Type: Uri
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

[Get-WssRemoteWebAccessLink](./Get-WssRemoteWebAccessLink.md)

[Remove-WssRemoteWebAccessLink](./Remove-WssRemoteWebAccessLink.md)


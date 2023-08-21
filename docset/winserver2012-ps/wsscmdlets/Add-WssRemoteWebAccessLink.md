---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/add-wssremotewebaccesslink?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-WssRemoteWebAccessLink

## SYNOPSIS
Adds a link to the home page of a Remote Web Access website.

## SYNTAX

```
Add-WssRemoteWebAccessLink -Text <String> -Url <Uri>
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssRemoteWebAccessLink](./Get-WssRemoteWebAccessLink.md)

[Remove-WssRemoteWebAccessLink](./Remove-WssRemoteWebAccessLink.md)


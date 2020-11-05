---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B68093A2-1860-4972-A4A5-97CE2AEBFA13
manager: dansimp
---

# Remove-WssRemoteWebAccessLink

## SYNOPSIS
Removes a link from the home page of a Remote Web Access website.

## SYNTAX

```
Remove-WssRemoteWebAccessLink -ID <String>
```

## DESCRIPTION
The **Remove-WssRemoteWebAccessLink** cmdlet removes a link from the home page of a Remote Web Access website.

To add a link to the home page of a Remote Web Access website, use the **Add-WssRemoteWebAccessLink** cmdlet.

## EXAMPLES

### Example 1: Remove a link from a home page
```
PS C:\> Remove-WssRemoteWebAccessLink -ID "23456789-ACAC-0330-9975-A246890654BC"
```

This command removes a link from a home page in Remote Web Access.

## PARAMETERS

### -ID
Specifies the key for the link you want to remove.
To obtain a list of IDs, use the **Get-RemoteWebAccessLink** cmdlet.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssRemoteWebAccessLink](./Add-WssRemoteWebAccessLink.md)

[Get-WssRemoteWebAccessLink](./Get-WssRemoteWebAccessLink.md)


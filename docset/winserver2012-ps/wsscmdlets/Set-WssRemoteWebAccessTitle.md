---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 61B1BBAC-9B38-439F-AADF-63832296BFE7
manager: dansimp
---

# Set-WssRemoteWebAccessTitle

## SYNOPSIS
Modifies the title string of a Remote Web Access website.

## SYNTAX

```
Set-WssRemoteWebAccessTitle -Title <String>
```

## DESCRIPTION
The **Set-WssRemoteWebAccessTitle** cmdlet modifies the title string of a Remote Web Access website in sbs_sbs8_2.
The title string appears in the middle of the logon page.

## EXAMPLES

### Example 1: Modify the title for Remote Web Access
```
PS C:\> Set-WssRemoteWebAccessTitle -Title "Contoso Remote Web Access"
```

This command modifies the title for a Remote Access Web website.

## PARAMETERS

### -Title
Specifies a title string for the Remote Web Access website.

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

[Get-WssRemoteWebAccessTitle](./Get-WssRemoteWebAccessTitle.md)


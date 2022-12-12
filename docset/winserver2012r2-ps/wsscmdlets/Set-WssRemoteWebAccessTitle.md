---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/set-wssremotewebaccesstitle?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssRemoteWebAccessTitle
---

# Set-WssRemoteWebAccessTitle

## SYNOPSIS
Modifies the title string of a Remote Web Access website.

## SYNTAX

```
Set-WssRemoteWebAccessTitle -Title <String> [<CommonParameters>]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssRemoteWebAccessTitle](./Get-WssRemoteWebAccessTitle.md)


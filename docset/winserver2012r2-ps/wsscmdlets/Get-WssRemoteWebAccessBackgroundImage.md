---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssremotewebaccessbackgroundimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssRemoteWebAccessBackgroundImage
---

# Get-WssRemoteWebAccessBackgroundImage

## SYNOPSIS
Retrieves the filename of the background image displayed on the Remote Web Access website.

## SYNTAX

```
Get-WssRemoteWebAccessBackgroundImage [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssRemoteWebAccessBackgroundImage** cmdlet retrieves the filename of the background image displayed on the logon page of the Remote Web Access website.

## EXAMPLES

### Example 1: Retrieve the filename of the background image
```
PS C:\> Get-WssRemoteWebAccessLink
```

This command retrieves the filename of the background image.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String
This cmdlet generates a string object that represents the filename of a customized background image.
The cmdlet does not generate any output if Remote Web Access uses the default image.

## NOTES

## RELATED LINKS

[Set-WssRemoteWebAccessBackgroundImage](./Set-WssRemoteWebAccessBackgroundImage.md)


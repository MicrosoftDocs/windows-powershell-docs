---
author: Kateyanne
external help file: ServerCore-help.xml
manager: dansimp
Module Name: ServerCore
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/servercore/get-displayresolution?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DisplayResolution

## SYNOPSIS
Shows the current display resolution for a Server Core server.

## SYNTAX

```
Get-DisplayResolution [<CommonParameters>]
```

## DESCRIPTION
The **Get-DisplayResolution** cmdlet shows the display resolution for Windows Server® 2012 in Server Core mode.
For a width of 1920 pixels and a height of 1080 pixels, the cmdlet displays 1920x1080.
You can use the **Set-DisplayResolution** cmdlet to change the resolution.

For more information about Server Core mode, see Configure and Manage Server Core Installationshttp://technet.microsoft.com/en-us/library/jj574091 (http://technet.microsoft.com/en-us/library/jj574091).

## EXAMPLES

### Example 1: Get display resolution
```
PS C:\> Get-DisplayResolution
1920x1080
```

This command gets the current display resolution, which is a width of 1920 and a height of 1080.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-DisplayResolution](./Set-DisplayResolution.md)


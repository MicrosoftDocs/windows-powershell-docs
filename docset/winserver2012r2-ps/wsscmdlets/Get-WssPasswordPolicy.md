---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wsspasswordpolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssPasswordPolicy
---

# Get-WssPasswordPolicy

## SYNOPSIS
Gets the current password policy for a server.

## SYNTAX

```
Get-WssPasswordPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssPasswordPolicy** cmdlet gets the current password policy for a server.

## EXAMPLES

### Example 1: Get the password policy for a server
```
PS C:\> Get-WssPasswordPolicy
```

This command gets the password policy from the server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Identity.PasswordPolicy
This cmdlet generates the password policy object for the server.

## NOTES

## RELATED LINKS


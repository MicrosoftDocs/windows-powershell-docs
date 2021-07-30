---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/new-wsspersonalfolder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WssPersonalFolder
---

# New-WssPersonalFolder

## SYNOPSIS
Adds a personal folder to the current server.

## SYNTAX

```
New-WssPersonalFolder [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-WssPersonalFolder** cmdlet adds a personal folder to the current server for a user.

## EXAMPLES

### Example 1: Add a personal folder
```
PS C:\> New-WssPersonalFolder -UserName "PattiFuller"
```

This command adds a personal folder for the user account named PattiFuller to the current server.

### 1:
```
PS C:\>
```

## PARAMETERS

### -UserName
Specifies the name of a user account.
The cmdlet adds a personal folder for the account that you specify to the current server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssPersonalFolder](./Get-WssPersonalFolder.md)


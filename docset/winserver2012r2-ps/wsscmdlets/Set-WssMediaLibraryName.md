---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssmedialibraryname?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssMediaLibraryName
---

# Set-WssMediaLibraryName

## SYNOPSIS
Changes the name of the Media Library.

## SYNTAX

```
Set-WssMediaLibraryName [-MediaLibraryName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMediaLibraryName** cmdlet changes the name of the Media Library for the current server.
You can use the Get-WssMediaLibraryName cmdlet to see the Media Library name.

## EXAMPLES

### Example 1: Rename a Media Library
```
PS C:\> Set-WssMediaLibraryName -MediaLibraryName "Accounting Library"
```

This command gives the Media Library the name Accounting Library.

## PARAMETERS

### -MediaLibraryName
Specifies a new name for the Media Library shared by the server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaLibraryName](./Get-WssMediaLibraryName.md)


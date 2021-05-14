---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/measure-wssfolder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-WssFolder
---

# Measure-WssFolder

## SYNOPSIS
Calculates the size of a given server folder.

## SYNTAX

```
Measure-WssFolder [-Folder] <Folder> [<CommonParameters>]
```

## DESCRIPTION
The **Measure-WssFolder** cmdlet calculates the size of a given server folder.

## EXAMPLES

### Example 1: Calculate the size of a server folder
```
PS C:\> $Pfolder = Get-WssFolder -Name "Projects01"
Measure-WssFolder -Folder $Pfolder
```

The first command gets the folder named Projects01, and stores the folder in the **$Pfolder** variable.
The second command calculates the size of the server folder stored in **$Pfolder**.

## PARAMETERS

### -Folder
Specifies the folder to calculate the size of.

```yaml
Type: Folder
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

### Microsoft.WindowsServerSolutions.Storage.CalculateFolderSizeRequest
This cmdlet generates the CalculateFolderSizeRequest object which can be used to calculate the size of a server folder.

## NOTES

## RELATED LINKS

[Get-WssFolder](./Get-WssFolder.md)

[Add-WssFolder](./Add-WssFolder.md)

[Set-WssFolder](./Set-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)


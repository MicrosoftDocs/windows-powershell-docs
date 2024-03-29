---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssfolder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssFolder
---

# Get-WssFolder

## SYNOPSIS
Gets an object that represents a folder.

## SYNTAX

### AllParamSet (Default)
```
Get-WssFolder [<CommonParameters>]
```

### ByNameParamSet
```
Get-WssFolder [-Name] <String> [<CommonParameters>]
```

### ByIdParamSet
```
Get-WssFolder [-ID] <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssFolder** cmdlet gets an object that represents a folder.
Specify a GUID for a specific folder.
If you do not specify a GUID, the cmdlet gets **Folder** objects for all the folders on current server.

## EXAMPLES

### Example 1: Get a folder by using a name
```
PS C:\> Get-WssFolder -Name "ProjectsWest"
```

This command gets the folder named ProjectsWest.

## PARAMETERS

### -ID
Specifies the GUID for a folder.

```yaml
Type: Guid
Parameter Sets: ByIdParamSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a folder.

```yaml
Type: String
Parameter Sets: ByNameParamSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Folder
This cmdlet generates the server **Folder** object.

## NOTES

## RELATED LINKS

[Set-WssFolder](./Set-WssFolder.md)

[Add-WssFolder](./Add-WssFolder.md)

[Move-WssFolder](./Move-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)


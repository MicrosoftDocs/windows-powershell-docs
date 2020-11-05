---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Add-WssFolder
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 40676510-8371-4728-8667-670E301CC593
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-WssFolder

## SYNOPSIS
Creates a new server folder.

## SYNTAX

### CustomFolderParams (Default)
```
Add-WssFolder [-Name] <String> [-Path] <String> [[-Description] <String>] [-HideFolderFromRemoteAccess]
 [[-ComputerName] <String>] [-KeepPermission] [<CommonParameters>]
```

### BuiltinFolderParams
```
Add-WssFolder [-Id] <Guid> [-Path] <String> [[-Description] <String>] [-HideFolderFromRemoteAccess]
 [[-ComputerName] <String>] [-KeepPermission] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssFolder** cmdlet creates a server folder.

## EXAMPLES

### Example 1: Create a server folder
```
PS C:\> Add-WssFolder -Name "ProjectsEast" -Path "D:\Contoso\Main"
```

This command creates the folder named ProjectsEast in D:\Contoso\Main.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the server folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HideFolderFromRemoteAccess
Specifies whether to hide the folder in Remote Desktop Web Access or Web service applications.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the GUID for a built-in server folder.
Specify this parameter to re-create a default shared folder, such as the Music folder or the Pictures folder.

```yaml
Type: Guid
Parameter Sets: BuiltinFolderParams
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeepPermission
Indicates that the folder keeps the permissions of the parent folder.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the folder.

```yaml
Type: String
Parameter Sets: CustomFolderParams
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Folder
This cmdlet returns the new server folder.

## NOTES

## RELATED LINKS

[Get-WssFolder](./Get-WssFolder.md)

[Set-WssFolder](./Set-WssFolder.md)

[Move-WssFolder](./Move-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)


---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Move-WssFolder
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 3835B800-FC6F-4DE5-9008-24698615C552
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Move-WssFolder

## SYNOPSIS
Moves a server folder to a different drive.

## SYNTAX

### OpParamSet (Default)
```
Move-WssFolder [-Force] [-Folder] <Folder> [-NewDrive] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CancelParamSet
```
Move-WssFolder [-Force] [-Folder] <Folder> [-Cancel] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Move-WssFolder** cmdlet moves a server folder to a different drive.

## EXAMPLES

### Example 1: Move a folder to a different drive
```
PS C:\> $Folder = Get-WssFolder -Name "ProjectsWest"
PS C:\> Move-WssFolder -Folder $Folder -NewDrive "E:\"
```

The first command gets the folder named ProjectsWest and stores it in the **$Folder** variable.

The second command moves the folder stored it in the **$Folder** variable from the current drive to the root directory on the drive E.

## PARAMETERS

### -Cancel
Indicates that the cmdlet attempts to cancel a move that is in progress.

```yaml
Type: SwitchParameter
Parameter Sets: CancelParamSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Folder
Specifies the name of a folder.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -NewDrive
Specifies the destination path for the folder on the new drive.

```yaml
Type: String
Parameter Sets: OpParamSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Folder

## NOTES

## RELATED LINKS

[Add-WssFolder](./Add-WssFolder.md)

[Get-WssFolder](./Get-WssFolder.md)

[Set-WssFolder](./Set-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)


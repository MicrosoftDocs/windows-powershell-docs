---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssfolder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssFolder
---

# Remove-WssFolder

## SYNOPSIS
Removes a server folder.

## SYNTAX

### ByNameParamSet (Default)
```
Remove-WssFolder -Name <String> [-Force] [-DeleteContents] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParamSet
```
Remove-WssFolder -Folder <Folder> [-Force] [-DeleteContents] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByIdParamSet
```
Remove-WssFolder -ID <Guid> [-Force] [-DeleteContents] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssFolder** cmdlet removes a server folder.
If you specify the **DeleteContents** parameter, the cmdlet deletes the contents of the server folder that you specify.
If you do not specify the **DeleteContents** parameter, the cmdlet stops sharing the contents of the server folder.

## EXAMPLES

### Example 1: Remove a server folder
```
PS C:\> Remove-WssFolder -Name "ProjectsNorth" -DeleteContents
```

This command removes the server folder named ProjectsNorth and deletes all the contents of the folder.

## PARAMETERS

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

### -DeleteContents
Indicates that the cmdlet deletes the contents of the server folder.

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

### -Folder
Specifies the name of a folder.

```yaml
Type: Folder
Parameter Sets: ByObjectParamSet
Aliases: 

Required: True
Position: Named
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

### -ID
Specifies the GUID for a folder.

```yaml
Type: Guid
Parameter Sets: ByIdParamSet
Aliases: 

Required: True
Position: Named
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
Position: Named
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

### Microsoft.WindowsServerSolutions.Storage.Folder

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Folder
This cmdlet generates an object that represents the removed folder.

## NOTES

## RELATED LINKS

[Add-WssFolder](./Add-WssFolder.md)

[Get-WssFolder](./Get-WssFolder.md)

[Set-WssFolder](./Set-WssFolder.md)

[Move-WssFolder](./Move-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)


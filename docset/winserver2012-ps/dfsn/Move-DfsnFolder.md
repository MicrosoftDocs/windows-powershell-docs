---
author: Kateyanne
external help file: DfsNamespaceFolder.cdxml-help.xml
manager: dansimp
Module Name: DFSN
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dfsn/move-dfsnfolder?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Move-DfsnFolder

## SYNOPSIS
Moves or renames a DFS namespace folder.

## SYNTAX

```
Move-DfsnFolder [-Path] <String> [-NewPath] <String> [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Move-DfsnFolder** cmdlet moves or renames a Distributed File System (DFS) namespace folder.

For more information about DFS namespaces, see Overview of DFS Namespaceshttp://technet.microsoft.com/library/cc730736 (http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Move a folder
```
PS C:\> Move-DfsnFolder -Path "\\Contoso\Western\Development\DesignDocuments" -NewPath "\\Contoso\Western\HumanResources\DesignDocuments"
```

This command moves the folder DesignDocuments to the location \\\\Contoso\Western\HumanResources.
After you run this command, the folder \\\\Contoso\Western\Development\DesignDocuments no longer exists.

### Example 2: Rename a folder
```
PS C:\> Move-DfsnFolder -Path "\\Contoso\AccountingSoftware\Software" -NewPath "\\Contoso\AccountingSoftware\LegacySoftware"
```

This command renames the folder Software in the \\\\Contoso\AccountingSoftware folder.
The new name is \\\\Contoso\AccountingSoftware\LegacySoftware.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
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

### -Force
Moves or renames a DFS namespace folder without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

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

### -NewPath
Specifies a path for the DFS namespace folder.
This cmdlet moves or renames the folder to have the path specified.
Do not specify an existing DFS namespace folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NewDfsPath, NewNamespacePath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path for a DFS namespace folder.
This cmdlet moves or renames the folder that has the path specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DfsPath, FolderPath, NamespacePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceFolder

## NOTES

## RELATED LINKS

[Get-DfsnFolder](./Get-DfsnFolder.md)

[New-DfsnFolder](./New-DfsnFolder.md)

[Remove-DfsnFolder](./Remove-DfsnFolder.md)

[Set-DfsnFolder](./Set-DfsnFolder.md)


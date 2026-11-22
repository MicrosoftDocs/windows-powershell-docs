---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceFolder.cdxml-help.xml
Module Name: DFSN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsn/move-dfsnfolder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-DfsnFolder
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

For more information about DFS namespaces, see
[Overview of DFS Namespaces](https://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Move a folder

```powershell
Move-DfsnFolder -Path '\\Contoso\Western\Development\DesignDocuments' -NewPath '\\Contoso\Western\HumanResources\DesignDocuments'
```

This command moves the folder DesignDocuments to the location `\\Contoso\Western\HumanResources`.
After you run this command, the folder `\\Contoso\Western\Development\DesignDocuments` no longer
exists.

### Example 2: Rename a folder

```powershell
Move-DfsnFolder -Path '\\Contoso\AccountingSoftware\Software' -NewPath '\\Contoso\AccountingSoftware\LegacySoftware'
```

This command renames the folder Software in the `\\Contoso\AccountingSoftware` folder. The new name
is `\\Contoso\AccountingSoftware\LegacySoftware`.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Moves or renames a DFS namespace folder without prompting you for confirmation. By default, the
cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewPath

Specifies a path for the DFS namespace folder. This cmdlet moves or renames the folder to have the
path specified. Do not specify an existing DFS namespace folder.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NewDfsPath, NewNamespacePath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Specifies the path for a DFS namespace folder. This cmdlet moves or renames the folder that has the
path specified.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DfsPath, FolderPath, NamespacePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`,
`-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`,
`-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-DfsnFolder](./Get-DfsnFolder.md)

[New-DfsnFolder](./New-DfsnFolder.md)

[Remove-DfsnFolder](./Remove-DfsnFolder.md)

[Set-DfsnFolder](./Set-DfsnFolder.md)

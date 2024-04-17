---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceFolder.cdxml-help.xml
Module Name: DFSN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsn/get-dfsnfolder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsnFolder
---

# Get-DfsnFolder

## SYNOPSIS
Gets settings for a DFS namespace folder.

## SYNTAX

```
Get-DfsnFolder [-Path] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION

The **Get-DfsnFolder** cmdlet gets configuration settings for a Distributed File System (DFS)
namespace folder. Specify a folder by using its path.

For more information about DFS namespaces, see
[Overview of DFS Namespaces](https://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Get settings for a specified folder

```powershell
Get-DfsnFolder -Path '\\Contoso\AccountingResources\LegacySoftware'
```

This command displays settings for the `\\Contoso\AccountingResources\LegacySoftware` folder.

### Example 2: Get settings for all folders in a DFS namespace

```powershell
Get-DfsnFolder -Path '\\Contoso\AccountingResources\*'
```

The command uses the wildcard to get settings for all the folders in the
`\\Contoso\AccountingResources` DFS namespace.

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

### -Path

Specifies a path for the folder. This cmdlet gets configuration settings for the DFS namespace
folder that has the path specified.

You can use DFS namespace with the wildcard character to get settings for all the folders in the
namespace. See the Examples section.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DfsPath, FolderPath, NamespacePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### CommonParameters

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`,
`-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`,
`-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

## NOTES

## RELATED LINKS

[Move-DfsnFolder](./Move-DfsnFolder.md)

[New-DfsnFolder](./New-DfsnFolder.md)

[Remove-DfsnFolder](./Remove-DfsnFolder.md)

[Set-DfsnFolder](./Set-DfsnFolder.md)

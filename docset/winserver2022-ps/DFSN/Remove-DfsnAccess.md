---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceAccess.cdxml-help.xml
Module Name: DFSN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsn/remove-dfsnaccess?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DfsnAccess
---

# Remove-DfsnAccess

## SYNOPSIS
Removes users and groups from the ACL for a folder in a DFS namespace.

## SYNTAX

```
Remove-DfsnAccess [-Path] <String> [-AccountName] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Remove-DfsnAccess** cmdlet removes users and groups from the access control list (ACL) for a
Distributed File System (DFS) namespace folder. When you remove a user from an ACL, the current
permissions in the ACL may still allow that user to access the folder.

For more information about DFS namespaces, see
[Overview of DFS Namespaces](https://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Remove a user from the ACL for a folder

```powershell
Remove-DfsnAccess -Path '\\Contoso\Software\Projects' -AccountName 'TSQA\PattiFuller'
```

This command removes the user TSQA\PattiFuller from the access control list of
`\\Contoso\Software\Projects`.

## PARAMETERS

### -AccountName

Specifies an array of user and group accounts. This cmdlet removes the accounts specified from the
ACL of a DFS namespace folder.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Account, User

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies a path for a DFS namespace folder. This cmdlet removes user accounts or group accounts
from the ACL of the folder specified.

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

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-DfsnAccess](./Get-DfsnAccess.md)

[Grant-DfsnAccess](./Grant-DfsnAccess.md)

[Revoke-DfsnAccess](./Revoke-DfsnAccess.md)

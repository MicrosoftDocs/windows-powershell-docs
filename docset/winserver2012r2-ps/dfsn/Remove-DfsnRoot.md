---
external help file: DfsNamespace.cdxml-help.xml
Module Name: DFSN
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/dfsn/remove-dfsnroot?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DfsnRoot
---

# Remove-DfsnRoot

## SYNOPSIS
Removes a DFS namespace.

## SYNTAX

```
Remove-DfsnRoot [-Path] <String> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DfsnRoot** cmdlet removes a Distributed File System (DFS) namespace.
When you remove a namespace, you remove all the folders in the namespace.
Users cannot use the DFS namespace folders after you remove the namespace.
This cmdlet does not delete the folders specified by DFS namespace targets or the files in those folders.

For more information about DFS namespaces, see Overview of DFS Namespaceshttp://technet.microsoft.com/library/cc730736 (http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Remove a DFS namespace
```
PS C:\> Remove-DfsnRoot -Path "\\Contoso\AccountingResources"
Confirm

Performing operation "Delete DFS Namespace" on Target "\\Contoso\AccountingResources"

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command removes the DFS namespace that has the path \\\\Contoso\AccountingResources.
The command does not include the **Force** parameter, so you must confirm the operation.

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
Removes a DFS namespace without prompting you for confirmation.
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

### -Path
Specifies the path for the root of a DFS namespace.
This cmdlet removes the namespace that has the path specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RootPath, root, namespace, NamespaceRoot

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

## NOTES

## RELATED LINKS

[Get-DfsnRoot](./Get-DfsnRoot.md)

[New-DfsnRoot](./New-DfsnRoot.md)

[Set-DfsnRoot](./Set-DfsnRoot.md)


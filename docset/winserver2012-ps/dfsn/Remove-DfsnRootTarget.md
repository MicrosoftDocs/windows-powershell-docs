---
external help file: DfsNamespaceRootTarget.cdxml-help.xml
Module Name: DFSN
online version: https://docs.microsoft.com/powershell/module/dfsn/remove-dfsnroottarget?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-DfsnRootTarget

## SYNOPSIS
Removes a target for a DFS namespace root.

## SYNTAX

```
Remove-DfsnRootTarget [-Path <String>] [-TargetPath] <String> [-Cleanup] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DfsnRootTarget** cmdlet removes a target for a Distributed File System (DFS) namespace root.
A folder target is the Universal Naming Convention (UNC) path of a shared folder or another namespace associated with a folder in a namespace.
The folder target is where data and content is stored.
This cmdlet deletes a target, but does not delete the contents of the folder target.

A DFS namespace root can have more than one root target.
If you remove the last root target associated with a DFS namespace root, this cmdlet deletes the namespace as well.
Users cannot use the DFS namespace path after you delete the namespace.

For more information about DFS namespaces, see Overview of DFS Namespaceshttps://technet.microsoft.com/library/cc730736 (https://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Remove a root target
```
PS C:\> Remove-DfsnRootTarget -TargetPath "\\Contoso-FS\AccountingSoftware" -Path "\\Contoso\AccountingSoftware"
```

This command removes the DFS root target path \\\\Contoso-FS\AccountingSoftware from the DFS namespace that has the path \\\\Contoso\AccountingSoftware.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Cleanup
Indicates that the cmdlet attempts to force a clean-up of the root target in Active Directory Domain Services (AD DS).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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

### -Path
Specifies the path for the root of a DFS namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DfsPath, NamespaceRoot

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetPath
Specifies a path for the folder target.
This cmdlet removes the folder target that has the path specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Target, DfsTarget, RootTargetPath

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DfsnRootTarget](./Get-DfsnRootTarget.md)

[New-DfsnRootTarget](./New-DfsnRootTarget.md)

[Set-DfsnRootTarget](./Set-DfsnRootTarget.md)


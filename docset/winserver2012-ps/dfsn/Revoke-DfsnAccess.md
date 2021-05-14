---
external help file: DfsNamespaceAccess.cdxml-help.xml
Module Name: DFSN
online version: https://docs.microsoft.com/powershell/module/dfsn/revoke-dfsnaccess?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Revoke-DfsnAccess

## SYNOPSIS
Revokes permissions for users to access and enumerate the contents of a DFS namespace folder.

## SYNTAX

```
Revoke-DfsnAccess [-Path] <String> [-AccountName] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-DfsnAccess** cmdlet revokes permissions for users and groups to access and enumerate the contents of a Distributed File System (DFS) namespace folder.
You can use the Get-DfsnAccess cmdlet to see the current permissions, and you can use the Grant-DfsnAccess cmdlet to grant permissions.

For a DFS namespace which has Access-based Enumeration enabled, users can see only the folders that they can access.

For more information about DFS namespaces, see Overview of DFS Namespaceshttp://technet.microsoft.com/library/cc730736 (http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Revoke permissions for a user
```
PS C:\> Revoke-DfsnAccess -Path "\\Contoso\Software\Projects" -AccountName "Western\SarahJones"
```

This command revokes permissions to access and view the contents of the DFS namespace folder \\\\Contoso\Software\Projects for a specified user.

## PARAMETERS

### -AccountName
Specifies an array of user and group accounts.
This cmdlet revokes permissions for the accounts specified.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Account, User

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -Path
Specifies a path for a DFS namespace folder.
This cmdlet revokes permissions for the folder specified.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceAccess

## NOTES

## RELATED LINKS

[Get-DfsnAccess](./Get-DfsnAccess.md)

[Grant-DfsnAccess](./Grant-DfsnAccess.md)

[Remove-DfsnAccess](./Remove-DfsnAccess.md)


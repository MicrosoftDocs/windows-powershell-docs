---
external help file: DfsNamespaceFolder.cdxml-help.xml
Module Name: DFSN
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/dfsn/get-dfsnfolder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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
The **Get-DfsnRoot** cmdlet gets configuration settings for a Distributed File System (DFS) namespace folder.
Specify a folder by using its path.

For more information about DFS namespaces, see Overview of DFS Namespaceshttp://technet.microsoft.com/library/cc730736 (http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Get settings for a specified folder
```
PS C:\> Get-DfsnFolder -Path "\\Contoso\AccountingResources\LegacySoftware"
```

This command displays settings for the \\\\Contoso\AccountingResources\LegacySoftware folder.

### Example 2: Get settings for all folders in a DFS namespace
```
PS C:\> Get-DfsnFolder -Path "\\Contoso\AccountingResources\*"
```

The command uses the wildcard to get settings for all the folders in the \\\\Contoso\AccountingResources DFS namespace.

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

### -Path
Specifies a path for the folder.
This cmdlet gets configuration settings for the DFS namespace folder that has the path specified.

You can use DFS namespace with the wildcard character to get settings for all the folders in the namespace.
See the Examples section.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceFolder[]

## NOTES

## RELATED LINKS

[Move-DfsnFolder](./Move-DfsnFolder.md)

[New-DfsnFolder](./New-DfsnFolder.md)

[Remove-DfsnFolder](./Remove-DfsnFolder.md)

[Set-DfsnFolder](./Set-DfsnFolder.md)


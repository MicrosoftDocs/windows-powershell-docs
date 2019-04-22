---
external help file: DfsNamespaceFolderTarget.cdxml-help.xml
ms.assetid: 9CC8E2DF-1EBF-4E77-A5EF-D4B60B5367E9
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
online version: 
schema: 2.0.0
---

# Get-DfsnFolderTarget

## SYNOPSIS
Gets settings for targets of a DFS namespace folder.

## SYNTAX

```
Get-DfsnFolderTarget [-Path] <String> [[-TargetPath] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsnFolderTarget** cmdlet gets settings for targets of a Distributed File System (DFS) namespace folder.
You can specify a DFS namespace folder path to see all the targets for that path.
You can specify a namespace path and a target path to see settings for a particular target.

For more information about DFS namespaces, see Overview of DFS Namespaceshttp://technet.microsoft.com/library/cc730736 (http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Get settings for a target
```
PS C:\> Get-DfsnFolderTarget -Path "\\Contoso\AccountingResources\LegacySoftware" -TargetPath "\\Contoso-FS\LegacySoftware"
NamespacePath         : \\Contoso\AccountingResources\LegacySoftware
ReferralPriorityClass : sitecost-normal
ReferralPriorityRank  : 0
State                 : Online
TargetPath            : \\Contoso-FS\LegacySoftware
PSComputerName        :
```

This command gets settings for the target of the \\\\Contoso\AccountingResources\LegacySoftware folder with the folder target of \\\\Contoso-FS\LegacySoftware.

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
Specifies a path for the root folder of a DFS namespace.

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

### -TargetPath
Specifies a path for the target of a DFS namespace folder.
This cmdlet gets settings for the target that has the path specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Target, DfsTarget, FolderTarget

Required: False
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceFolderTarget[]

## NOTES

## RELATED LINKS

[New-DfsnFolderTarget](./New-DfsnFolderTarget.md)

[Remove-DfsnFolderTarget](./Remove-DfsnFolderTarget.md)

[Set-DfsnFolderTarget](./Set-DfsnFolderTarget.md)


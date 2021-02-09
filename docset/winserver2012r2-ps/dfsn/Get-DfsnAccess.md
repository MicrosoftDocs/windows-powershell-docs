---
external help file: DfsNamespaceAccess.cdxml-help.xml
Module Name: DFSN
online version: 
schema: 2.0.0
title: Get-DfsnAccess
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 17623C97-B384-4998-85FC-71BD5E581F95
---

# Get-DfsnAccess

## SYNOPSIS
Gets permissions for a DFS namespace folder.

## SYNTAX

```
Get-DfsnAccess [-Path] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsnAccess** cmdlet gets account names and access types for users and groups that have permissions for a Distributed File System (DFS) namespace folder.
You can use the Grant-DfsnAccess cmdlet and the Revoke-DfsnAccess cmdlet to manage access for DFS namespace folders.

For more information about DFS namespaces, see Overview of DFS Namespaceshttp://technet.microsoft.com/library/cc730736 (http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Get permissions for a folder
```
PS C:\> Get-DfsnAccess -Path "\\Contoso\Software\Projects"
```

This command gets permissions for a DFS namespace folder that has the path \\\\Contoso\Software\Projects.

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
Specifies a path for a DFS namespace folder.
This cmdlet gets permissions for the folder specified.
Provide a complete path for a folder, not a partial or relative path.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceAccess[]

## NOTES

## RELATED LINKS

[Grant-DfsnAccess](./Grant-DfsnAccess.md)

[Remove-DfsnAccess](./Remove-DfsnAccess.md)

[Revoke-DfsnAccess](./Revoke-DfsnAccess.md)


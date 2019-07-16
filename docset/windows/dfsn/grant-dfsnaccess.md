---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceAccess.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Grant-DfsnAccess
ms.reviewer:
ms.assetid: 956730DE-562C-46BB-817C-3949CDDB6E4F
---

# Grant-DfsnAccess

## SYNOPSIS
Grants permissions to users and groups to access a DFS namespace folder.

## SYNTAX

```
Grant-DfsnAccess [-Path] <String> [-AccountName] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-DfsnAccess** cmdlet grants permissions to users and groups for a Distributed File System (DFS) namespace folder.
This cmdlet grants permissions to access a folder and to enumerate its contents.
You can use the **Get-DfsnAccess** cmdlet to see the current permissions, and you can use the **Revoke-DfsnAccess** cmdlet to revoke permissions.

For a DFS namespace which has Access-based enumeration enabled, users can see only the folders that they can access.

For more information about DFS namespaces, see [Overview of DFS Namespaces](http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Grant permissions to a user
```
PS C:\> Grant-DfsnAccess -Path "\\Contoso\Software\Projects" -AccountName "TSQA\PattiFuller"

AccessType     : Enumerate
AccountName    : TSQA\PattiFuller
NamespacePath  : \\Contoso\Software\Projects
PSComputerName :
```

This command grants the user TSQA\PattiFuller permissions for the folder \\\\Contoso\Software\Projects.

## PARAMETERS

### -AccountName
Specifies an array of user and group accounts.
This cmdlet grants permissions to the accounts specified.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Account, user

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](http://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](http://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies a path for a DFS namespace folder.
This cmdlet grants permissions to access the folder specified.

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
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceAccess

## NOTES

## RELATED LINKS

[Get-DfsnAccess](./Get-DfsnAccess.md)

[Remove-DfsnAccess](./Remove-DfsnAccess.md)

[Revoke-DfsnAccess](./Revoke-DfsnAccess.md)


---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceRootTarget.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DfsnRootTarget
ms.reviewer:
ms.assetid: 6380961C-9497-472E-99EA-C328EC2D7344
---

# Get-DfsnRootTarget

## SYNOPSIS
Gets settings for root targets of a DFS namespace.

## SYNTAX

```
Get-DfsnRootTarget [-Path] <String> [[-TargetPath] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsnRootTarget** cmdlet gets settings for root targets of a Distributed File System (DFS) namespace.
You can specify a DFS namespace path to see all the root targets for that namespace.
You can specify a namespace path and a target path to see settings for a single root target.

For more information about DFS namespaces, see [Overview of DFS Namespaces](http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Get root targets for a DFS namespace
```
PS C:\> Get-DfsnRootTarget -Path "\\Contoso\AccountingSoftware"
```

This command gets the DFS namespace root targets for the namespace that has the path \\\\Contoso\AccountingSoftware.

### Example 2: Get a specified root target
```
PS C:\> Get-DfsnRootTarget -Path "\\Contoso\AccountingSoftware" -TargetPath "\\Contoso-FS\Software"
```

This command gets a single root target, specified by using the path \\\\Contoso\AccountingSoftware and the target path \\\\Contoso-FS\Software.

## PARAMETERS

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

### -Path
Specifies a path for the root folder of a DFS namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DfsPath, NamespaceRoot

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetPath
Specifies a path for the root folder target of a DFS namespace.
This cmdlet gets settings for the root target that has the path specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Target, DfsTarget, RootTargetPath

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceRootTarget

## NOTES

## RELATED LINKS

[New-DfsnRootTarget](./New-DfsnRootTarget.md)

[Remove-DfsnRootTarget](./Remove-DfsnRootTarget.md)

[Set-DfsnRootTarget](./Set-DfsnRootTarget.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BranchCacheOrchestrator.cdxml-help.xml
Module Name: BranchCache
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/branchcache/publish-bcfilecontent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-BCFileContent
---

# Publish-BCFileContent

## SYNOPSIS
Generates hashes for files in shared folders.

## SYNTAX

```
Publish-BCFileContent [-Path] <String[]> [-UseVersion <UInt32>] [-StageData] [-StagingPath <String>]
 [-ReferenceFile <String>] [-Force] [-Recurse] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Publish-BCFileContent** cmdlet generates hashes, also called content information, for files in shared folders on file servers that have BranchCache enabled and the BranchCache for Network Files role service installed.

This cmdlet is also used to stage data for the creation of a data preloading package.
Run this cmdlet with the *StageData* parameter on one or more collections of files.
Run the **Export-BCCachePackage** cmdlet to produce a data package that contains all the staged data.
You can import that data package on remote hosted cache computers.

## EXAMPLES

### Example 1: Hash the contents of a folder for export
```
PS C:\> Publish-BCFileContent -Path "D:\share" -StageData
```

This command hashes the contents of D:\share and adds the data to a cache package that can later be exported and sent to a remote hosted cache server.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Forces the command to run without asking for user confirmation.

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
Specifies the file path or the path of a folder that contains files that this cmdlet hashes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Recurse
Indicates that hashes are created for content in subfolders.
If you do not specify this parameter, this cmdlet creates hashes only for content in the top folder.

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

### -ReferenceFile
Specifies a reference file from a previous run.
A reference file contains a list of identifiers that describe the data in a data package.
If you specify a reference file, this cmdlet excludes all data described in that file from the output.
You can use a reference files to create data packages that only contain the changes from the previous time a data package was created.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StageData
Indicates that this cmdlet saves data to a staging area for future export using the **Export-BCCachePackage** cmdlet.
If you do not specify this parameter, hashes are generated for data, but the data is not prepared for export.

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

### -StagingPath
Specifies a temporary folder to which this cmdlet saves the staging data.
If you do not specify a location, this cmdlet uses a default location on the local hard disk.
Use this parameter if a large data package is being created that must be housed on a separate hard disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -UseVersion
Specifies the version of the BranchCache hashing scheme to use.
If the version specified is 1, content information is generated according to the scheme used by Windows 7 clients.
If version specified is 2, content information is generated according to the more efficient hashing scheme used by client computers that run operating systems later than Windows® 7.

```yaml
Type: UInt32
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Export-BCCachePackage](./Export-BCCachePackage.md)


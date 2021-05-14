---
external help file: BranchCacheOrchestrator.cdxml-help.xml
Module Name: BranchCache
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/branchcache/publish-bcfilecontent?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-BCFileContent
---

# Publish-BCFileContent

## SYNOPSIS
Generates hashes, also called content information, for files in shared folders on a file server that have BranchCache enabled and the BranchCache for Network Files role service installed.

## SYNTAX

```
Publish-BCFileContent [-Path] <String[]> [-UseVersion <UInt32>] [-StageData] [-StagingPath <String>]
 [-ReferenceFile <String>] [-Force] [-Recurse] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Publish-BCFileContent** cmdlet generates hashes, also called content information, for files in shared folders on file servers that have BranchCache enabled and the BranchCache for Network Files role service installed.

This cmdlet is also used to stage data for the creation of a data preloading package.
Run this cmdlet with the **StageData** parameter on one or more collections of files, then call the Export-BCCachePackage cmdlet to produce a data package containing all the staged data.
This data package can be imported on remote hosted cache computers.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Publish-BCFileContent -Path D:\share -StageData
```

This example hashes the contents of D:\share and adds the data to a cache package, that can later be exported and sent to a remote hosted cache server.

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
Runs the cmdlet without prompting for confirmation.

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
Specifies the file path, or the path to a directory containing files, that will be hashed.

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
Specifies that hashes are created for content in subfolders.
If you do not use this parameter, then hashes are created only for content in the top folder and no hashes are created for content in subfolders.

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
If a reference file is supplied, all data described in that file will be excluded from the output of this cmdlet.
Reference files can be used to create data packages that only contain the changes from the previous time a data package was created including the target data.

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
Specifies that the data should be saved to a staging area for future export using the Export-BCCachePackage cmdlet.
Use this parameter if a data package for export is being created.
If this parameter in not specified, then hashes are generated for data, but the data is not prepared for export.

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
Specifies a temporary folder to which to output the staging data.
If a location is not specified, then a default location on the local hard drive is used.
Use this parameter if a large data package is being created that must be housed on a separate hard drive.

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
If version specified is `1`, then content information is generated according to the scheme used by firstref_client_7 clients.
If version specified is `2`, then content information is generated according to the more efficient hashing scheme used by client computers that are running operating systems later than Windows® 7.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Export-BCCachePackage](./Export-BCCachePackage.md)


---
external help file: BranchCacheOrchestrator.cdxml-help.xml
Module Name: BranchCache
online version: https://learn.microsoft.com/powershell/module/branchcache/publish-bcwebcontent?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Publish-BCWebContent

## SYNOPSIS
Creates hashes for web content when deploying content servers that are running Windows Server® 8 Beta with the Web Services (IIS) server role installed.

## SYNTAX

```
Publish-BCWebContent [-Path] <String[]> [-UseVersion <UInt32>] [-StageData] [-StagingPath <String>]
 [-ReferenceFile <String>] [-Force] [-Recurse] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Publish-BCWebContent** cmdlet creates hashes for web content when content servers are deployed running Windows Server® 2012 with the Web Services (IIS) server role installed.
In addition, the web server must be configured as a BranchCache content server by installing the BranchCache feature.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Publish-BCWebContent -Path D:\inetpub\wwwroot -Recurse
```

This example pre-hashes the contents of wwwroot, so that hashes are available as soon as requests are made.

### EXAMPLE 2
```
PS C:\>Publish-BCWebContent -Path D:\inetpub\wwwroot -StageData
```

This example adds data to a data package, that can later be exported and preloaded on a remote hosted cache server.

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
By default the cmdlet asks for confirmation from the user before proceeding.

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
If this parameter is not used, then hashes are created only for content in the top folder; no hashes are created for content in subfolders..

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
Specifies that the hashes should be saved to a staging area for future export.
Use this parameter if a data package is created for export.
If this parameter is not specified, then hashes are generated for data, but data is not prepared for export.

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
Specifies the folder location where staging data is stored.

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
If the specified version is `1`, then the content information is generated according to the scheme used by firstref_client_7clients.
If the specified version is `2`, then the content information is generated according to the more efficient hashing scheme used by client computers that are running operating systems later than Windows® 7.

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

[Disable-BC](./Disable-BC.md)

[Reset-BC](./Reset-BC.md)


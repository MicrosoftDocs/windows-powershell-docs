---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BranchCacheOrchestrator.cdxml-help.xml
Module Name: BranchCache
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/branchcache/remove-bcdatacacheextension?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-BCDataCacheExtension
---

# Remove-BCDataCacheExtension

## SYNOPSIS
Deletes a data cache file.

## SYNTAX

### Path (Default)
```
Remove-BCDataCacheExtension [-Force] [-Path] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DataCacheExtension
```
Remove-BCDataCacheExtension [-Force] [-DataCacheExtension] <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-BCDataCacheExtension** cmdlet deletes the cache file that is specified.

## EXAMPLES

### Example 1: Remove data cache extensions
```
PS C:\> Get-BCDataCacheExtension | Where-Object -FilterScript {$_.MaxCacheSizeAsPercentageOfDiskVolume -Eq 10} | Remove-BCDataCacheExtension
```

This command removes data cache extensions configured to occupy ten percent of disk volume.
The command uses the **Get-BCDataCacheExtension** cmdlet to get cache extensions, and passes the results to the **Where-Object** cmdlet by using the pipeline operator.
That cmdlet passes on objects that meet its requirement to the current cmdlet.
That cmdlet removes those extensions.

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

### -DataCacheExtension
Specifies the data cache extension that this cmdlet removes.
You can obtain a BranchCache **MSFT_NetBranchCacheDataCacheExtension** CIM object by using the **Get-BCDataCacheExtension** cmdlet.

Specify either this parameter or the *Path* parameter, but not both.

```yaml
Type: CimInstance[]
Parameter Sets: DataCacheExtension
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies the data cache extension that this cmdlet removes.

Specify either this parameter or the *DataCacheExtension* parameter, but not both.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: 1
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

[Add-BCDataCacheExtension](./Add-BCDataCacheExtension.md)

[Get-BCDataCacheExtension](./Get-BCDataCacheExtension.md)


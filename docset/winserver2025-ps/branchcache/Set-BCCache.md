---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BranchCacheOrchestrator.cdxml-help.xml
Module Name: BranchCache
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/branchcache/set-bccache?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BCCache
---

# Set-BCCache

## SYNOPSIS
Modifies the cache file configuration.

## SYNTAX

### Path (Default)
```
Set-BCCache [-MoveTo <String>] [-Percentage <UInt32>] [-SizeBytes <UInt64>] [-Defragment] [-Force] [-PassThru]
 [[-Path] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Cache
```
Set-BCCache [-MoveTo <String>] [-Percentage <UInt32>] [-SizeBytes <UInt64>] [-Defragment] [-Force] [-PassThru]
 [-Cache] <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-BCCache** cmdlet modifies the cache file configuration.
Use the *Cache* parameter to specify which cache this cmdlet configures.

## EXAMPLES

### Example 1: Move a cache file
```
PS C:\> Set-BCCache -Path "C:\datacache" -MoveTo "D:\datacache"
```

This command moves the cache file from C:\datacache to D:\datacache.

### Example 2: Change the size of a cache file
```
PS C:\> Get-BCDataCacheExtension | Where-Object -FilterScript {$_.MaxCacheSizeAsPercentageOfDiskVolume -Eq 10} | Set-BCCache -Percentage 20
```

This command increases data cache files from 10 percent to 20 percent of the disk size.
The command uses the **Get-BCDataCacheExtension** cmdlet to get cache extensions, and passes the results to the **Where-Object** cmdlet by using the pipeline operator.
That cmdlet passes on objects that meet its requirement to the current cmdlet.
That cmdlet modifies those extensions.

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

### -Cache
Specifies the cache this cmdlet modifies.

```yaml
Type: CimInstance[]
Parameter Sets: Cache
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### -Defragment
Indicates that this cmdlet defragments the cache.
Fragmented cache files store data less effectively.
The BranchCache service detects cache fragmentation and raises an event in the Windows Event Log when it is time to defragment the cache.

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

### -MoveTo
Specifies the new location on disk for this cache file.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
Specifies the path of the cache file.

```yaml
Type: String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Percentage
Specifies the new size of this cache file.
The size is a percentage of the disk.

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

### -SizeBytes
Specifies the new size of the cache file.

```yaml
Type: UInt64
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimV2\MSFT_NetBranchCacheCache[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Clear-BCCache](./Clear-BCCache.md)

[Get-BCDataCacheExtension](./Get-BCDataCacheExtension.md)


---
external help file: BranchCacheOrchestrator.cdxml-help.xml
ms.assetid: 9F39B44E-399E-4116-85B7-58B60A4EFC84
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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

### EXAMPLE 1
```
PS C:\>Get-BCDataCacheExtension | Where-Object -FilterScript {$_.MaxCacheSizeAsPercentageOfDiskVolume -Eq 10} | Remove-BCDataCacheExtension
```

This example removes data cache extensions configured to occupy 10% of disk volume.

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

### -DataCacheExtension
Specifies the data cache extension that should be removed.
A BranchCache CimInstance#root\StandardCimv2\MSFT_NetBranchCacheDataCacheExtension CIM object can be obtained using the Get-BCDataCacheExtension cmdlet. 

If a value for this parameter is specified, then do not specify a value for the **Path** parameter, or an error will occur.
Use either this parameter or the **Path** parameter, but not both.

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
Removes the data cache extension at the location that you specify.
If a value for this parameter is specified, then do not specify a value for the **DataCacheExtension** parameter, or an error will occur.
Use either this parameter or the **DataCacheExtension** parameter, but not both

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Add-BCDataCacheExtension](./Add-BCDataCacheExtension.md)

[Get-BCDataCacheExtension](./Get-BCDataCacheExtension.md)


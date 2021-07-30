---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wsswinsatcpuscore?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssWinSatCpuScore
---

# Set-WssWinSatCpuScore

## SYNOPSIS
Modifies the Windows Experience Index processor subscore.

## SYNTAX

```
Set-WssWinSatCpuScore [-WinSatCpuScore] <Double> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssWinSatCpuScore** cmdlet modifies the Windows Experience Index (WinSAT) processor subscore.

## EXAMPLES

### Example 1: Modify the WinSAT score
```
PS C:\> Set-WssWinSatCpuScore -WinSatCpuScore 1
```

This command modifies the WinSAT score.

## PARAMETERS

### -WinSatCpuScore
Specifies a WinSAT CPU score.

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssWinSatCpuScore](./Get-WssWinSatCpuScore.md)


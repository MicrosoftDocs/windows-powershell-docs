---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/set-wsswinsatcpuscore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssWinSatCpuScore

## SYNOPSIS
Modifies the Windows Experience Index processor subscore.

## SYNTAX

```
Set-WssWinSatCpuScore [-WinSatCpuScore] <Double>
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssWinSatCpuScore](./Get-WssWinSatCpuScore.md)


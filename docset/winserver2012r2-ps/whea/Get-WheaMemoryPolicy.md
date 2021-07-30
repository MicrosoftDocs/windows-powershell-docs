---
external help file: Microsoft.Windows.Whea.WheaMemoryPolicy.dll-Help.xml
Module Name: WHEA
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/whea/get-wheamemorypolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WheaMemoryPolicy
---

# Get-WheaMemoryPolicy

## SYNOPSIS
Retrieves the Windows Hardware Error Architecture (WHEA) memory policies in effect on a local or remote computer.

## SYNTAX

```
Get-WheaMemoryPolicy [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### Example: Get the WHEA memory policy settings from the local computer
```
PS C:\>Get-WHEAMemoryPolicy
DisableOffline : False
DisablePFA : False
PersistMemoryOffline : True
PFAPageCount : 64
PFAErrorThreshold : 16
PFATimeOut : 86400
```

Return WHEA memory policy values from the local computer, as a WheaMemoryPolicy object.

## PARAMETERS

### -ComputerName
Name of the remote computer from which to retrieve policy information.
If no computer name is specified, the command returns the policy of the local computer.
You can use cn as an alias for ComputerName.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS


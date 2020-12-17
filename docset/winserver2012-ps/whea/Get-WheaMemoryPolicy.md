---
external help file: Microsoft.Windows.Whea.WheaMemoryPolicy.dll-Help.xml
ms.assetid: A9175E75-42E5-4E39-9DD5-8C37F7761214
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WheaMemoryPolicy

## SYNOPSIS
Gets WHEA memory policies.

## SYNTAX

```
Get-WheaMemoryPolicy [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WheaMemoryPolicy** cmdlet gets the Windows Hardware Error Architecture (WHEA) memory policies in effect on a local or remote computer.

## EXAMPLES

### Example 1: Get WHEA memory policy settings from the local computer
```
PS C:\>Get-WHEAMemoryPolicy
DisableOffline : False 
DisablePFA : False 
PersistMemoryOffline : True 
PFAPageCount : 64 
PFAErrorThreshold : 16 
PFATimeOut : 86400
```

This command gets WHEA memory policy values (as a **WheaMemoryPolicy** object) from the local computer.

## PARAMETERS

### -ComputerName
Specifies the name of the remote computer from which to get policy information.
If no computer name is specified, the command returns the policy of the local computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WheaMemoryPolicy

## NOTES

## RELATED LINKS


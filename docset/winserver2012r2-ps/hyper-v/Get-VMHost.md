---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmhost?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMHost
---

# Get-VMHost

## SYNOPSIS
Gets a Hyper-V host.

## SYNTAX

```
Get-VMHost [[-ComputerName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMHost** cmdlet gets a Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMHost
```

Gets the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: .
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.Host

## NOTES

## RELATED LINKS


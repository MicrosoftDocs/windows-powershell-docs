---
external help file: NetworkControllerFc-help.xml
Module Name: NetworkControllerFc
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkcontrollerfc/add-networkcontrolleronfailoverclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetworkControllerOnFailoverClusterNode
---

# Add-NetworkControllerOnFailoverClusterNode

## SYNOPSIS
Adds a new Node to the NetworkController

## SYNTAX

```
Add-NetworkControllerOnFailoverClusterNode [-NodeName] <String> [<CommonParameters>]
```

## DESCRIPTION

Adds a new Node to the NetworkController. This performs the following tasks.

- Copies the binaries to the New Node
- Creates the Services for the SDN Microservices
- Creates the Http.Sys SSL bindings
- Adds an entry to the Node ThumbPrint list

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -NodeName

{{ Fill NodeName Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

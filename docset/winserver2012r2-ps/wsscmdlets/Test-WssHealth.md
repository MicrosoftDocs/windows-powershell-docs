---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/test-wsshealth?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WssHealth
---

# Test-WssHealth

## SYNOPSIS
Performs an evaluation of all health checks.

## SYNTAX

```
Test-WssHealth [<CommonParameters>]
```

## DESCRIPTION
The **Test-WssHealth** cmdlet performs an evaluation of all health checks.
If the cmdlet finds no outstanding health alerts, it returns a value of $True.
If it finds outstanding health alerts, it returns a value of $False.

## EXAMPLES

### Example 1: Perform a health check evaluation
```
PS C:\> Test-WssHealth
```

This command performs evaluation of all health checks.
The command returns a value of $True or $False, depending on whether it finds outstanding alerts.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean

## NOTES

## RELATED LINKS


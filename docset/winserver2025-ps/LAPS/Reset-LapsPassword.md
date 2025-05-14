---
description: Causes Windows Local Administrator Password Solution (LAPS) to immediately rotate the password for the currently managed local account.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/reset-lapspassword?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Reset-LapsPassword
---

# Reset-LapsPassword

## SYNOPSIS
Causes Windows Local Administrator Password Solution (LAPS) to immediately rotate the password for
the currently managed local account.

## SYNTAX

```
Reset-LapsPassword [<CommonParameters>]
```

## DESCRIPTION

The `Reset-LapsPassword` cmdlet tells LAPS to immediately rotate the password for the currently
managed local account. This operation is performed regardless of the state of the current password,
for example it doesn't matter whether the current password is considered expired or not.

> [!IMPORTANT]
> This cmdlet is intended and recommended only for rare situations that require an
> immediate password rotation, for example as a response to a machine security breach situation.
> Excessively frequent usage of this cmdlet isn't recommended.

The cmdlet doesn't return detailed information about the results of the operation. See
[Use Windows LAPS event logs](https://go.microsoft.com/fwlink/?linkid=2234103) for more information
on querying the resultant event log entries to get specific information on the outcome of the
operation.

## EXAMPLES

### Example 1

```powershell
Reset-LapsPassword
```

This example forces immediate rotation of the managed local account.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Windows LAPS Overview](https://go.microsoft.com/fwlink/?linkid=2233901)

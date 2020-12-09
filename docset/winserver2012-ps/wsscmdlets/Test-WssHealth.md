---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 8CE2BB10-E6EB-4C19-9962-775FC951E566
manager: dansimp
---

# Test-WssHealth

## SYNOPSIS
Performs an evaluation of all health checks.

## SYNTAX

```
Test-WssHealth
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

## INPUTS

## OUTPUTS

### bool

## NOTES

## RELATED LINKS


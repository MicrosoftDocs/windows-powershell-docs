---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/set-netintenttracing?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIntentTracing
---

# Set-NetIntentTracing

## SYNOPSIS
Starts or stops ATC tracing sessions on the host.

## SYNTAX

```
Set-NetIntentTracing [-StopTracing] [[-ComputerName] <String>]
```

## DESCRIPTION

The `Set-NetIntentTracing` cmdlet starts or stops ATC tracing sessions on the
specified host. Tracing sessions are useful for diagnosing issues related to
network intents by capturing relevant data.

## EXAMPLES

### Example 1

```powershell
Set-NetIntentTracing -ComputerName "Server01"
```

This example starts an ATC tracing session on the computer named `Server01`.

### Example 2

```powershell
Set-NetIntentTracing -StopTracing -ComputerName "Server01"
```

This example stops an ATC tracing session on the computer named `Server01`.

## PARAMETERS

### -StopTracing

Indicates that the cmdlet should stop the tracing session instead of starting it.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies the name of the computer on which to start or stop the tracing
session. If this parameter is not specified, the cmdlet operates on the local
computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### [switch] $StopTracing, switch to stop tracing

### [string] $ComputerName, target computer name

## OUTPUTS

## NOTES

## RELATED LINKS

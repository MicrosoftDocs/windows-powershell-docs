---
external help file: MSFT_NetTeredoState.cdxml-help.xml
Module Name: NetworkTransition
online version: 
schema: 2.0.0
title: Get-NetTeredoState
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 862A11AC-F6D2-43F1-9C47-354304610627
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NetTeredoState

## SYNOPSIS
Retrieves the active Teredo state of the local computer.

## SYNTAX

```
Get-NetTeredoState [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetTeredoState** cmdlet retrieves the active Teredo state of the local computer.

If Teredo is not active, then this cmdlet does not return an object.

## EXAMPLES

### Example 1: Get the active Teredo state
```
PS C:\>Get-NetTeredoState
```

This command retrieves the active Teredo state of the local computer.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTeredoState
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
This cmdlet returns a Teredo state object.

## NOTES

## RELATED LINKS

[Get-NetTeredoConfiguration](./Get-NetTeredoConfiguration.md)

[Reset-NetTeredoConfiguration](./Reset-NetTeredoConfiguration.md)

[Set-NetTeredoConfiguration](./Set-NetTeredoConfiguration.md)


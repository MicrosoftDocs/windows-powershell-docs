---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIpHTTPsState.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/get-netiphttpsstate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIPHttpsState
---

# Get-NetIPHttpsState

## SYNOPSIS
Gets the active IP-HTTPS state of a computer.

## SYNTAX

```
Get-NetIPHttpsState [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetIPHttpsState** cmdlet gets the active IP-HTTPS state of a computer.

If IP-HTTPS is not active, then this cmdlet does not return an object.

## EXAMPLES

### Example 1: Get the active IP-HTTPS state
```
PS C:\>Get-NetIPHttpsState
```

This command gets the active IP-HTTPS state of the computer.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIpHTTPsState
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

This cmdlet returns an IP-HTTPS state object.

## NOTES

## RELATED LINKS

[Get-NetIPHttpsConfiguration](./Get-NetIPHttpsConfiguration.md)

[New-NetIPHttpsConfiguration](./New-NetIPHttpsConfiguration.md)

[Remove-NetIPHttpsConfiguration](./Remove-NetIPHttpsConfiguration.md)

[Rename-NetIPHttpsConfiguration](./Rename-NetIPHttpsConfiguration.md)

[Reset-NetIPHttpsConfiguration](./Reset-NetIPHttpsConfiguration.md)

[Set-NetIPHttpsConfiguration](./Set-NetIPHttpsConfiguration.md)


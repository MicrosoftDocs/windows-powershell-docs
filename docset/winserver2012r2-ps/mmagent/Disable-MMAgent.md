---
external help file: ps_mmagent_v1.0.cdxml-help.xml
Module Name: MMAgent
online version: 
schema: 2.0.0
title: Disable-MMAgent
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A6142E5E-104A-4A91-B3A5-55E9F3078DBA
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-MMAgent

## SYNOPSIS
Disables application launch prefetching, operation recorder API functionality, page combining, and application prelaunch.

## SYNTAX

```
Disable-MMAgent [-ApplicationLaunchPrefetching] [-ApplicationPreLaunch] [-OperationAPI] [-PageCombining]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-MMAgent** cmdlet disables any or all of the following features:
- Application launch prefetching 
- Operation recorder API functionality
- Page combining

- Application prelaunching

For more details on what these features do, see Enable-MMAgent.

## EXAMPLES

### Example 1: Disable application launch prefetching
```
PS C:\> Disable-MMAgent -ApplicationLaunchPrefetching
```

This command disables application launch prefetching on the local computer.

## PARAMETERS

### -ApplicationLaunchPrefetching
Disables application launch prefetching.

If you do not specify this parameter, application launch prefetching remains in its current state, either enabled or disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: alp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationPreLaunch
Disables application prelaunch.

If you do not specify this parameter, application prelaunch remains in its current state, either enabled or disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: apl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -OperationAPI
Disables operation recorder API functionality.

If you do not specify this parameter, operation recorder API functionality remains in its current state, either enabled or disabled.

For more information about the Operation Recorder API, see Operation Recorderhttp://msdn.microsoft.com/library/windows/desktop/hh437575(v=VS.85).aspx on MSDN (http://msdn.microsoft.com/library/windows/desktop/hh437575(v=VS.85).aspx)

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: oa

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PageCombining
Disables page combining.

If you do not specify this parameter, page combining remains in its current state, either enabled or disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: pc

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Debug-MMAppPrelaunch](./Debug-MMAppPrelaunch.md)

[Enable-MMAgent](./Enable-MMAgent.md)

[Get-MMAgent](./Get-MMAgent.md)

[Set-MMAgent](./Set-MMAgent.md)


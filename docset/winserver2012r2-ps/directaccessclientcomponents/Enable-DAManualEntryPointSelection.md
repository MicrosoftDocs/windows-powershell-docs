---
external help file: MSFT_DASiteTableEntry.cdxml-help.xml
Module Name: DirectAccessClientComponents
online version: 
schema: 2.0.0
title: Enable-DAManualEntryPointSelection
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E0662F30-27FF-4182-87A0-567CAB097C51
---

# Enable-DAManualEntryPointSelection

## SYNOPSIS
Allows a user to manually choose which DirectAccess entry point to use for connectivity.

## SYNTAX

```
Enable-DAManualEntryPointSelection -EntryPointName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Enable-DAManualEntryPointSelection** allows a user to manually choose which DirectAccess entry point to use for connectivity.
This cmdlet succeeds only when the client computer is outside of the corporate network perimeter, and DirectAccess is deployed.

Computers configured for multisite DirectAccess automatically pick the best entry point to use for connectivity.
A user might want to override the entry point that is automatically selected; for example, to help troubleshoot network connectivity.
This cmdlet allows a user to manually choose a DirectAccess entry point.

You can prevent a user from overriding the automatic selection by using Group Policy.
For more information about using Group Policy to restrict automatic selection changes, see Get-DAClientExperienceConfiguration.

## EXAMPLES

### Example: Enable manual DirectAccess site selection
```
PS C:\> Enable-DAManualEntryPointSelection -EntryPointName "Redmond"
```

This cmdlet enables the entry point named **Redmond**

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryPointName
Specifies the name of the DirectAccess entry point to enable.
The specified entry point is used for DirectAccess connectivity until the computer joins a new network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Disable-DAManualEntryPointSelection](./Disable-DAManualEntryPointSelection.md)


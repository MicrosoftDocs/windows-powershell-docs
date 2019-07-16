---
external help file: MSFT_NetNatSession.cdxml-help.xml
Module Name: NetNat
online version: 
schema: 2.0.0
title: Get-NetNatSession
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 368F5A0E-2F50-45EC-A17F-A1710E40CEF9
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Get-NetNatSession

## SYNOPSIS
Gets all active NAT sessions.

## SYNTAX

```
Get-NetNatSession [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetNatSession** cmdlet gets all active network address translation (NAT) sessions on a computer.

## EXAMPLES

### Example 1: Get all active NAT sessions
```
PS C:\> Get-NetNatSession
```

This command gets all NAT sessions on the local computer.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetNatSession

## NOTES

## RELATED LINKS

[Get-NetNat](./Get-NetNat.md)


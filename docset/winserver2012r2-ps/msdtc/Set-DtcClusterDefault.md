---
external help file: MSFT_DtcClusterDefaultTask_v1.0.cdxml-help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Set-DtcClusterDefault
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E3AB0237-DE07-409C-A23F-2DDC2B4B042D
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Set-DtcClusterDefault

## SYNOPSIS
Sets the cluster default transactions coordinator.

## SYNTAX

```
Set-DtcClusterDefault -DtcResourceName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DtcClusterDefault** cmdlet sets the cluster default transactions coordinator.

## EXAMPLES

### Example 1: Specify a resource
```
PS C:\> Set-DtcClusterDefault -DtcResourceName "ClusteredDtcResource"
```

This command sets the default cluster DTC to the resource named ClusteredDtcResource.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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

### -DtcResourceName
Specifies the name of the Distributed Transaction Coordinator (DTC) cluster resource that needs to be set as default cluster TM.
This command is supported only on clustered nodes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

## OUTPUTS

### String
This cmdlet returns the virtual server name of the cluster default transactions coordinator.

## NOTES

## RELATED LINKS

[Get-DtcClusterDefault](./Get-DtcClusterDefault.md)


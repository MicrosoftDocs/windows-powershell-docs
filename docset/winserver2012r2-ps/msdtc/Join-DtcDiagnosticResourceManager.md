---
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Join-DtcDiagnosticResourceManager
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 68A0664C-705E-48D4-8A80-F036FA000ECE
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Join-DtcDiagnosticResourceManager

## SYNOPSIS
Enlists a diagnostic Resource Manager for a transaction object.

## SYNTAX

```
Join-DtcDiagnosticResourceManager [-Transaction] <DtcDiagnosticTransaction> [[-ComputerName] <String>]
 [[-Port] <Int32>] [-Volatile] [<CommonParameters>]
```

## DESCRIPTION
The **Join-DtcDiagnosticResourceManager** cmdlet enlists a diagnostic Resource Manager (RM) for a specified transaction object.
The transaction first needs to be sent to the RM.

## EXAMPLES

### Example 1: Enlist a new diagnostic transaction
```
PS C:\>$Transaction = New-DtcDiagnosticTransaction
PS C:\> Join-DtcDiagnosticResourceManager -Transaction $Transaction
```

The first command creates a transaction by using the New-DtcDiagnosticTransaction cmdlet, and then stores that transaction in the **$Transaction** variable.

The second command enlists the transaction stored in **$Transaction** to a diagnostic resource manager.

## PARAMETERS

### -ComputerName
Specifies the host name of the computer on which the RM runs.
If you do not specify a host name, this cmdlet uses the name of the local computer.

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

### -Port
Specifies the listening port of the test RM.
If you do not specify a port number, this cmdlet uses the name of the local computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transaction
Specifies the transaction object on which to enlist the RM.

```yaml
Type: DtcDiagnosticTransaction
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Volatile
Indicates that this cmdlet makes a volatile enlistment.
If you do not specify this parameter, the cmdlet makes a durable enlistment.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-DtcDiagnosticResourceManager](./Start-DtcDiagnosticResourceManager.md)

[Stop-DtcDiagnosticResourceManager](./Stop-DtcDiagnosticResourceManager.md)

[New-DtcDiagnosticTransaction](./New-DtcDiagnosticTransaction.md)


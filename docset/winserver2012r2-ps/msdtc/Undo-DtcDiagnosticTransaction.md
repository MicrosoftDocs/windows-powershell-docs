---
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Undo-DtcDiagnosticTransaction
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: F93A43CE-6DBD-4CBA-B8EE-970858959D7E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Undo-DtcDiagnosticTransaction

## SYNOPSIS
Invokes the Abort process on the specified transaction.

## SYNTAX

```
Undo-DtcDiagnosticTransaction [-Transaction] <DtcDiagnosticTransaction> [<CommonParameters>]
```

## DESCRIPTION
The **Undo-DtcDiagnosticTransaction** cmdlet invokes the Abort process on the specified transaction.

## EXAMPLES

### Example 1: Undo a DTC diagnostic transaction
```
PS C:\>$Tx = New-DtcDiagnosticTransaction
PS C:\> Undo-DtcDiagnosticTransaction -Transaction $Tx
```

This command creates a new diagnostic transaction and assigns it to a variable.

The second command undoes the transaction.

## PARAMETERS

### -Transaction
Specifies the **DtcDiagnosticTransaction** object on which to invoke the Abort process.
You can use the pipeline operator to pass this parameter value to the cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Complete-DtcDiagnosticTransaction](./Complete-DtcDiagnosticTransaction.md)

[New-DtcDiagnosticTransaction](./New-DtcDiagnosticTransaction.md)

[Receive-DtcDiagnosticTransaction](./Receive-DtcDiagnosticTransaction.md)

[Send-DtcDiagnosticTransaction](./Send-DtcDiagnosticTransaction.md)


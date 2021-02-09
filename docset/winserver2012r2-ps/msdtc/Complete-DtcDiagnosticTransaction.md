---
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Complete-DtcDiagnosticTransaction
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: CBF5A008-9FAC-491B-9580-0E98369B2CE4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Complete-DtcDiagnosticTransaction

## SYNOPSIS
Invokes the Commit process if the specified transaction is the root transaction; otherwise, invokes the Complete method on a transaction object.

## SYNTAX

```
Complete-DtcDiagnosticTransaction [-Transaction] <DtcDiagnosticTransaction> [<CommonParameters>]
```

## DESCRIPTION
The **Complete-DtcDiagnosticTransaction** cmdlet invokes the Commit process if the specified transaction is the root transaction; otherwise, it invokes the **Complete** method on the transaction object specified by the **DtcDiagnosticTransaction** object.

## EXAMPLES

### Example 1: Complete a DTC diagnostic transaction
```
PS C:\>$Tx = New-DtcDiagnosticTransaction
PS C:\> Complete-DtcDiagnosticTransaction -Transaction $Tx
```

The first command creates a new DTC diagnostic transaction and assigns it to a variable.

The second command invokes the Commit process of the transaction.

## PARAMETERS

### -Transaction
Specifies the **DtcDiagnosticTransaction** object on which to invoke the **Complete** method or to commit.

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

### Default
Specifies the **DtcDiagnosticTransaction** object on which to invoke the **Complete** method.
You can use the pipeline operator to pass this parameter value to the cmdlet.

## OUTPUTS

## NOTES

## RELATED LINKS

[New-DtcDiagnosticTransaction](./New-DtcDiagnosticTransaction.md)

[Receive-DtcDiagnosticTransaction](./Receive-DtcDiagnosticTransaction.md)

[Send-DtcDiagnosticTransaction](./Send-DtcDiagnosticTransaction.md)

[Undo-DtcDiagnosticTransaction](./Undo-DtcDiagnosticTransaction.md)


---
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Send-DtcDiagnosticTransaction
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: EF593C1C-5927-4E90-982D-35C9F9F386F8
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Send-DtcDiagnosticTransaction

## SYNOPSIS
Propagates a transaction to a specified diagnostic Resource Manager.

## SYNTAX

```
Send-DtcDiagnosticTransaction [-Transaction] <DtcDiagnosticTransaction> [[-ComputerName] <String>]
 [[-Port] <Int32>] [[-PropagationMethod] <DtcTransactionPropagation>] [<CommonParameters>]
```

## DESCRIPTION
The **Send-DtcDiagnosticTransaction** cmdlet propagates a transaction to a specified diagnostic Resource Manager (RM).
Use the **PropagationMethod** parameter to specify the propagation method.

## EXAMPLES

### Example 1: Send a DTC diagnostic transaction
```
PS C:\>$Tx = New-DtcDiagnosticTransaction
PS C:\> Send-DtcDiagnosticTransaction -Transaction $Tx -ComputerName "Host1" -PropagationMethod Push
```

The first command creates a new DTC diagnostic transaction and assigns it to a variable.

The second command sends the diagnostic transaction to an RM running on the computer named Host1.

## PARAMETERS

### -ComputerName
Specifies the host name of the computer on which the RM is running.
If you do not specify a host name, the cmdlet uses the name of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Port
Specifies the listening port of the test RM.
If you do not specify a port number, the cmdlet uses the name of the local computer.

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

### -PropagationMethod
Specifies the propagation mechanism, pull or push, to use.
The default is pull.

```yaml
Type: DtcTransactionPropagation
Parameter Sets: (All)
Aliases: 
Accepted values: Pull, Push

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transaction
Specifies the **DtcDiagnosticTransaction** object to use in the transaction propagation.
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

[Undo-DtcDiagnosticTransaction](./Undo-DtcDiagnosticTransaction.md)


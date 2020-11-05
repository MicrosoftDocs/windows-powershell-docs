---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: F93A43CE-6DBD-4CBA-B8EE-970858959D7E
manager: dansimp
---

# Undo-DtcDiagnosticTransaction

## SYNOPSIS
Invokes the Abort process on the specified transaction.

## SYNTAX

```
Undo-DtcDiagnosticTransaction [-Transaction] <DtcDiagnosticTransaction>
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Complete-DtcDiagnosticTransaction](./Complete-DtcDiagnosticTransaction.md)

[New-DtcDiagnosticTransaction](./New-DtcDiagnosticTransaction.md)

[Receive-DtcDiagnosticTransaction](./Receive-DtcDiagnosticTransaction.md)

[Send-DtcDiagnosticTransaction](./Send-DtcDiagnosticTransaction.md)


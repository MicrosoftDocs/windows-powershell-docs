---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://learn.microsoft.com/powershell/module/msdtc/complete-dtcdiagnostictransaction?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Complete-DtcDiagnosticTransaction

## SYNOPSIS
Invokes the Commit process if the specified transaction is the root transaction; otherwise, invokes the Complete method on a transaction object.

## SYNTAX

```
Complete-DtcDiagnosticTransaction [-Transaction] <DtcDiagnosticTransaction>
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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


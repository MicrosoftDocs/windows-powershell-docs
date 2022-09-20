---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://learn.microsoft.com/powershell/module/msdtc/new-dtcdiagnostictransaction?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-DtcDiagnosticTransaction

## SYNOPSIS
Creates a new transaction in a Transaction Manager on the local computer.

## SYNTAX

```
New-DtcDiagnosticTransaction [[-Timeout] <Int32>] [-IsolationLevel]
```

## DESCRIPTION
The **New-DtcDiagnosticTransaction** cmdlet creates a new transaction in a Transaction Manager (TM) on the local computer.
By default it creates a transaction on the default transaction manager on the local computer.
This cmdlet returns a transaction object that you can pass to other cmdlets.

## EXAMPLES

### Example 1: Create a diagnostic transaction
```
PS C:\>New-DtcDiagnosticTransaction -Timeout 60 -IsolationLevel Serializable
Id
--
4625a5a3-af35-465d-a331-f224d79e4c85
```

This command creates a new serializable diagnostic transaction with a timeout of 60 seconds.

## PARAMETERS

### -IsolationLevel
Specifies the isolation level for a transaction.The acceptable values for this parameter are:

- Serializable 
- RepeatableRead
- ReadCommitted
- ReadUncommitted
- Snapshot
- Chaos 

If you do not specify this parameter, the cmdlet uses the default **IsolationLevel** value specified in the **System.Transactions.Transaction** object.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Serializable, RepeatableRead, ReadCommitted, ReadUncommitted, Snapshot, Chaos, Unspecified

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout
Specifies the timeout, in seconds, for the transaction.
If you do not specify this parameter, the cmdlet uses the default timeout value specified in the **System.Transactions.Transaction** object.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
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

[Receive-DtcDiagnosticTransaction](./Receive-DtcDiagnosticTransaction.md)

[Send-DtcDiagnosticTransaction](./Send-DtcDiagnosticTransaction.md)

[Undo-DtcDiagnosticTransaction](./Undo-DtcDiagnosticTransaction.md)


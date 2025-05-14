---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/new-dtcdiagnostictransaction?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-DtcDiagnosticTransaction
---

# New-DtcDiagnosticTransaction

## SYNOPSIS
Creates a new transaction in a Transaction Manager on the local computer.

## SYNTAX

```
New-DtcDiagnosticTransaction [[-Timeout] <Int32>] [[-IsolationLevel] <IsolationLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **New-DtcDiagnosticTransaction** cmdlet creates a new transaction in a Transaction Manager (TM) on the local computer.
By default it creates a transaction on the default transaction manager on the local computer.
This cmdlet returns a transaction object that you can pass to other cmdlets.

## EXAMPLES

### Example 1: Create a diagnostic transaction
```
PS C:\> New-DtcDiagnosticTransaction -Timeout 60 -IsolationLevel Serializable
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
Type: IsolationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Serializable, RepeatableRead, ReadCommitted, ReadUncommitted, Snapshot, Chaos, Unspecified

Required: False
Position: 1
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
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Complete-DtcDiagnosticTransaction](./Complete-DtcDiagnosticTransaction.md)

[Receive-DtcDiagnosticTransaction](./Receive-DtcDiagnosticTransaction.md)

[Send-DtcDiagnosticTransaction](./Send-DtcDiagnosticTransaction.md)

[Undo-DtcDiagnosticTransaction](./Undo-DtcDiagnosticTransaction.md)


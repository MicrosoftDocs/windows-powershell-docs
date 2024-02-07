---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/receive-dtcdiagnostictransaction?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-DtcDiagnosticTransaction
---

# Receive-DtcDiagnosticTransaction

## SYNOPSIS
Propagates a transaction from a given diagnostic Resource Manager.

## SYNTAX

```
Receive-DtcDiagnosticTransaction [[-ComputerName] <String>] [[-Port] <Int32>]
 [[-PropagationMethod] <DtcTransactionPropagation>] [<CommonParameters>]
```

## DESCRIPTION
The **Receive-DtcDiagnosticTransaction** cmdlet propagates a transaction from a specified diagnostic Resource Manager (RM).
A transaction is created on the specified RM and propagated to the Windows PowerShell® client using either pull or push propagation.
Use the **PropagationMethod** parameter to specify the propagation mechanism.

## EXAMPLES

### Example 1: Receive a diagnostic transaction
```powershell
PS C:\> Receive-DtcDiagnosticTransaction -ComputerName "Host1" -Port 17123 -PropagationMethod Pull
```
```output
Id
--
d23fd4b1-1b54-486a-9e9f-a92550a19ce2
```

This command pulls a diagnostic transaction from Host1 port 17123.

## PARAMETERS

### -ComputerName
Specifies the host name of the computer on which the RM runs.
If you do not specify a host name, this cmdlet uses the name of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Port
Specifies the listening port of the test RM.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: 3002
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Complete-DtcDiagnosticTransaction](./Complete-DtcDiagnosticTransaction.md)

[New-DtcDiagnosticTransaction](./New-DtcDiagnosticTransaction.md)

[Send-DtcDiagnosticTransaction](./Send-DtcDiagnosticTransaction.md)

[Undo-DtcDiagnosticTransaction](./Undo-DtcDiagnosticTransaction.md)


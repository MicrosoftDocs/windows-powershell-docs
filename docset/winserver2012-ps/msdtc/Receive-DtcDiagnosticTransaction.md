---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://learn.microsoft.com/powershell/module/msdtc/receive-dtcdiagnostictransaction?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Receive-DtcDiagnosticTransaction

## SYNOPSIS
Propagates a transaction from a given diagnostic Resource Manager.

## SYNTAX

```
Receive-DtcDiagnosticTransaction [[-ComputerName] <String>] [[-Port] <Int32>] [-PropagationMethod]
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
Position: 1
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
Position: 2
Default value: 3002
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropagationMethod
Specifies the propagation mechanism, pull or push, to use.
The default is pull.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Pull, Push

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Complete-DtcDiagnosticTransaction](./Complete-DtcDiagnosticTransaction.md)

[New-DtcDiagnosticTransaction](./New-DtcDiagnosticTransaction.md)

[Send-DtcDiagnosticTransaction](./Send-DtcDiagnosticTransaction.md)

[Undo-DtcDiagnosticTransaction](./Undo-DtcDiagnosticTransaction.md)


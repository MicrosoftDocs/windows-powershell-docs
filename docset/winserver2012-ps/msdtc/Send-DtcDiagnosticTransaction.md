---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: EF593C1C-5927-4E90-982D-35C9F9F386F8
manager: dansimp
---

# Send-DtcDiagnosticTransaction

## SYNOPSIS
Propagates a transaction to a specified diagnostic Resource Manager.

## SYNTAX

```
Send-DtcDiagnosticTransaction [-Transaction] <DtcDiagnosticTransaction> [[-ComputerName] <String>]
 [[-Port] <Int32>] [-PropagationMethod]
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
Position: 2
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
Position: 3
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
Position: 4
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

[Undo-DtcDiagnosticTransaction](./Undo-DtcDiagnosticTransaction.md)


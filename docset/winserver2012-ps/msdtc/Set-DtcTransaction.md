---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: BA7E24DE-F643-43A0-8F61-60AA7ACF6A1E
manager: dansimp
---

# Set-DtcTransaction

## SYNOPSIS
Modifies the state of a transaction.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DtcTransaction [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>] [-Abort]
 -TransactionId <Guid>
```

### UNNAMED_PARAMETER_SET_2
```
Set-DtcTransaction [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>] [-Commit]
 -TransactionId <Guid>
```

### UNNAMED_PARAMETER_SET_3
```
Set-DtcTransaction [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>] [-Trace]
 -TransactionId <Guid>
```

### UNNAMED_PARAMETER_SET_4
```
Set-DtcTransaction [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>] [-Forget]
 -TransactionId <Guid>
```

## DESCRIPTION
The **Set-DtcTransaction** cmdlet modifies the state of a transaction in the Distributed Transaction Coordinator (DTC) host-level properties stored in the registry.

## EXAMPLES

### Example 1: Set a trace for a transaction
```
PS C:\> Set-DtcTransaction -DtcName "Local" -Trace -TransactionId 2E6E62E0-044B-4DFE-9A8B-B69CFF5C9E26
```

This command sets a trace for the specified transaction.

## PARAMETERS

### -Abort
Indicates to abort the specified transaction.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Commit
Specifies to commit the specified transaction.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DtcName
Specifies a DTC instance.
The cmdlet modifies the state of a transaction in the DTC host-level properties for this instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Forget
Indicates to forget the specified transaction.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trace
Specifies to trace the transaction.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransactionId
Specifies the TransactionId of the transaction to modify.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DtcTransaction](./Get-DtcTransaction.md)


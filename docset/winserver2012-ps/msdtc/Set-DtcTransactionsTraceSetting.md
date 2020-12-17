---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: FB2F0685-6D63-4745-B68A-423EF189C193
manager: dansimp
---

# Set-DtcTransactionsTraceSetting

## SYNOPSIS
Modifies the DTC transactions trace setting of the host.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DtcTransactionsTraceSetting [-AbortedTransactionsTracingEnabled <Boolean>] [-CimSession <CimSession[]>]
 [-LongLivedTransactionsTracingEnabled <Boolean>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DtcTransactionsTraceSetting [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -AllTransactionsTracingEnabled <Boolean>
```

## DESCRIPTION
The **Set-DtcTransactionsTraceSetting** cmdlet modifies the Distributed Transaction Coordinator (DTC) transactions trace setting of the host.

## EXAMPLES

### Example 1: Enable trace settings for all transactions
```
PS C:\> Set-DtcTransactionsTraceSetting -AllTransactionsTracingEnabled $True
```

This command enables trace settings for all transactions.

## PARAMETERS

### -AbortedTransactionsTracingEnabled
Indicates whether to enable tracing for aborted transactions.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllTransactionsTracingEnabled
Indicates whether to enable tracing for all transactions.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

### -LongLivedTransactionsTracingEnabled
Indicates whether to enable tracing for long-lived transactions.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DtcTransactionsTraceSetting](./Get-DtcTransactionsTraceSetting.md)


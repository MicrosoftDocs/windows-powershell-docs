---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://docs.microsoft.com/powershell/module/msdtc/join-dtcdiagnosticresourcemanager?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Join-DtcDiagnosticResourceManager

## SYNOPSIS
Enlists a diagnostic Resource Manager for a transaction object.

## SYNTAX

```
Join-DtcDiagnosticResourceManager [-Transaction] <DtcDiagnosticTransaction> [[-ComputerName] <String>]
 [[-Port] <Int32>] [-Volatile]
```

## DESCRIPTION
The **Join-DtcDiagnosticResourceManager** cmdlet enlists a diagnostic Resource Manager (RM) for a specified transaction object.
The transaction first needs to be sent to the RM.

## EXAMPLES

### Example 1: Enlist a new diagnostic transaction
```
PS C:\>$Transaction = New-DtcDiagnosticTransaction
PS C:\> Join-DtcDiagnosticResourceManager -Transaction $Transaction
```

The first command creates a transaction by using the New-DtcDiagnosticTransaction cmdlet, and then stores that transaction in the **$Transaction** variable.

The second command enlists the transaction stored in **$Transaction** to a diagnostic resource manager.

## PARAMETERS

### -ComputerName
Specifies the host name of the computer on which the RM runs.
If you do not specify a host name, this cmdlet uses the name of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies the listening port of the test RM.
If you do not specify a port number, this cmdlet uses the name of the local computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transaction
Specifies the transaction object on which to enlist the RM.

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

### -Volatile
Indicates that this cmdlet makes a volatile enlistment.
If you do not specify this parameter, the cmdlet makes a durable enlistment.

```yaml
Type: SwitchParameter
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

[Start-DtcDiagnosticResourceManager](./Start-DtcDiagnosticResourceManager.md)

[Stop-DtcDiagnosticResourceManager](./Stop-DtcDiagnosticResourceManager.md)

[New-DtcDiagnosticTransaction](./New-DtcDiagnosticTransaction.md)


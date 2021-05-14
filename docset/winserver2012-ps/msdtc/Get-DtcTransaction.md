---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://docs.microsoft.com/powershell/module/msdtc/get-dtctransaction?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DtcTransaction

## SYNOPSIS
Gets information about transactions being handled by the DTC instance.

## SYNTAX

```
Get-DtcTransaction [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DtcTransaction** cmdlet gets information about transactions being handled by the Distributed Transaction Coordinator (DTC) instance.
Use the **DtcName** parameter to specify the DTC instance.

## EXAMPLES

### Example 1: Get DTC transactions
```
PS C:\>Get-DtcTransaction -DtcName "Local"
TransactionId  : b61f99fd-3c83-451c-9d92-4e790ca59585
Description    : xxxxxxxxxx
State          : Active
IsolationLevel : 0
Parent         :
```

This command queries the transactions handled by the local DTC instance.

## PARAMETERS

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

### -DtcName
Specifies a DTC instance.
The cmdlet gets  transaction information for this DTC instance.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet gets the information for transactions handled by the local DTC instance.

```yaml
Type: String
Parameter Sets: (All)
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

[Set-DtcTransaction](./Set-DtcTransaction.md)


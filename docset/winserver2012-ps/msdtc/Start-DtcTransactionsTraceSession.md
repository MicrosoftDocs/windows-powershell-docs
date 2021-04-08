---
author: Kateyanne
external help file: MsDTC_Cmdlets.xml
manager: dansimp
Module Name: MsDTC
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msdtc/start-dtctransactionstracesession?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-DtcTransactionsTraceSession

## SYNOPSIS
Starts a new DTC transactions trace session for the host.

## SYNTAX

```
Start-DtcTransactionsTraceSession [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Start-DtcTransactionsTraceSession** cmdlet starts a new Distributed Transaction Coordinator (DTC) transactions trace session for the host.
If there is an active session, this cmdlet prompts you before it stops the current session and starts a new trace session.

## EXAMPLES

### Example 1: Start a trace session
```
PS C:\> Start-DtcTransactionsTraceSession
```

This command starts a trace session.

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

[Get-DtcTransactionsTraceSession](./Get-DtcTransactionsTraceSession.md)

[Set-DtcTransactionsTraceSession](./Set-DtcTransactionsTraceSession.md)

[Stop-DtcTransactionsTraceSession](./Stop-DtcTransactionsTraceSession.md)

[Write-DtcTransactionsTraceSession](./Write-DtcTransactionsTraceSession.md)


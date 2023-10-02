---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://learn.microsoft.com/powershell/module/msdtc/reset-dtclog?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Reset-DtcLog

## SYNOPSIS
Resets the log file of a DTC instance.

## SYNTAX

```
Reset-DtcLog [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Reset-DtcLog** cmdlet resets the log file of a Distributed Transaction Coordinator (DTC) instance.
You can use the **DtcName** parameter to specify a DTC instance.
This cmdlet also recreates the transactions log with the existing settings and restarts the DTC instance.

## EXAMPLES

### Example 1: Reset a DTC log
```
PS C:\>Reset-DtcLog -DtcName "Local" -Confirm:$False -WhatIf:$False
```

This command resets the log file for the Local DTC instance.

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
The cmdlet resets the log file for this instance.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet resets the log file for the local DTC instance.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DtcLog](./Get-DtcLog.md)

[Set-DtcLog](./Set-DtcLog.md)


---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://docs.microsoft.com/powershell/module/msdtc/set-dtclog?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DtcLog

## SYNOPSIS
Modifies the log file settings of a DTC instance.

## SYNTAX

```
Set-DtcLog [-CimSession <CimSession[]>] [-DtcName <String>] [-MaxSizeInMB <UInt32>] [-Path <String>]
 [-SizeInMB <UInt32>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DtcLog** cmdlet modifies the log file settings of a Distributed Transaction Coordinator (DTC) instance.
Use the **DtcName** parameter to specify a DTC instance.
This cmdlet also recreates the transactions log with new settings and restarts the DTC instance.

## EXAMPLES

### Example 1: Set the log file path and file size
```
PS C:\> Set-DtcLog -Path "C:\Windows\system32\MSDtc\NewLog\" -SizeInMB 32 -MaxSizeInMB 1024
PS C:\> Get-DtcLog
MaxSizeInMB      : 1024
Path             : C:\Windows\system32\MSDtc\NewLog
SizeInMB         : 32
```

The first command sets the path for the DTC log file and specifies the file size.
The second command confirms the change.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
The cmdlet modifies the log file for this instance.
If you do not specify this parameter, or if you specify a value of   Local, this cmdlet modifies the log file for the local DTC instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -MaxSizeInMB
Specifies the maximum file size of the new log file in MB.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the physical or network path to store the new log file.
If a log file already exists in the specified path it is overwritten.

```yaml
Type: String
Parameter Sets: (All)
Aliases: p

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -SizeInMB
Specifies the initial file allocation size of the new log file in megabytes.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
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

[Reset-DtcLog](./Reset-DtcLog.md)


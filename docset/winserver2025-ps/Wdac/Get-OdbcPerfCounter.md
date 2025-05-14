---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_OdbcPerfCounterTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/get-odbcperfcounter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OdbcPerfCounter
---

# Get-OdbcPerfCounter

## SYNOPSIS
Gets connection pooling Performance Monitor counters.

## SYNTAX

```
Get-OdbcPerfCounter [[-Platform] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-OdbcPerfCounter** cmdlet gets the Open Database Connectivity (ODBC) connection pooling performance monitor counters.

For more information about ODBC and performance counters, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) and [ODBC Performance Counters](https://msdn.microsoft.com/en-us/library/windows/desktop/ms709288.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Get ODBC Performance Counter setting on a 32-bit platform
```
PS C:\> Get-OdbcPerfCounter -Platform "32-bit"
```

This command gets the ODBC Performance Counter setting on a 32-bit platform.

### Example 2: Get ODBC Performance Counter setting on both platforms
```
PS C:\> Get-OdbcPerfCounter
```

This command gets the ODBC Performance Counter setting on both 32-bit and 64-bit platforms.

### Example 3: Store ODBC Performance Counter setting for a 32-bit platform
```
PS C:\> $PerfCounter = Get-OdbcPerfCounter -Platform "32-bit"
```

This command gets the ODBC Performance Counter setting on a 32-bit platform, and then stores the result in the $PerfCounter variable.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Platform
Specifies the platform architecture.
This cmdlet gets the ODBC connection pooling Performance Monitor counters that belong to the architecture that this parameter specifies.
The acceptable values for this parameter are:

- 32-bit
- 64-bit
- All

The default value is All.
If you run this cmdlet in a remote CIM session, this parameter refers to the platform architecture on the remote computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: 32-bit, 64-bit, All

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcPerfCounter[]

## NOTES

## RELATED LINKS

[Disable-OdbcPerfCounter](./Disable-OdbcPerfCounter.md)

[Enable-OdbcPerfCounter](./Enable-OdbcPerfCounter.md)


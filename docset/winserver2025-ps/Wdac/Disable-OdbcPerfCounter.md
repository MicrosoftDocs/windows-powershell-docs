---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_OdbcPerfCounterTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/disable-odbcperfcounter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-OdbcPerfCounter
---

# Disable-OdbcPerfCounter

## SYNOPSIS
Disables connection pooling Performance Monitor counters.

## SYNTAX

### InputObject (Default)
```
Disable-OdbcPerfCounter [-PassThru] [-InputObject] <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Platform
```
Disable-OdbcPerfCounter [-PassThru] [[-Platform] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-OdbcPerfCounter** cmdlet disables the Open Database Connectivity (ODBC) connection pooling Performance Monitor counters for ODBC connection pooling.

For more information about ODBC and performance counters, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) and [ODBC Performance Counters](https://msdn.microsoft.com/en-us/library/windows/desktop/ms709288.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Disable Performance Counter on a 32-bit platform
```
PS C:\> Disable-OdbcPerfCounter -Platform "32-bit"
```

This command disables the ODBC Performance Counter setting on a 32-bit platform.

### Example 2: Disable Performance Counter both platforms
```
PS C:\> Disable-OdbcPerfCounter -Platform "All"
```

This command disables the ODBC Performance Counter setting on both 32-bit and 64-bit platforms.

### Example 3: Enable and disable Performance Counter on a 32-bit platform
```
PS C:\> $PerfCounter = Enable-OdbcPerfCounter -Platform "32-bit" -PassThru
PS C:\> Disable-OdbcPerfCounter -InputObject $PerfCounter
```

The first command enables the ODBC Performance Counter setting on 32-bit platform, and then stores the result in the $PerfCounter variable.
After you run the first command, you can run ODBC applications that use pooling.

The second command disables the ODBC Performance Counter setting specified by **$PerfCounter**.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject
Aliases: PerfCounter

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Platform
Specifies the platform architecture.
This cmdlet disables the ODBC connection pooling Performance Monitor counters that belong to the architecture that the parameter specifies.
The acceptable values for this parameter are:

- 32-bit
- 64-bit
- All

If you run this cmdlet in a remote CIM session, this parameter refers to the platform architecture on the remote computer.

```yaml
Type: String
Parameter Sets: Platform
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

[Enable-OdbcPerfCounter](./Enable-OdbcPerfCounter.md)

[Get-OdbcPerfCounter](./Get-OdbcPerfCounter.md)


---
external help file: MSFT_OdbcPerfCounterTask_v1.0.cdxml-help.xml
Module Name: Wdac
online version: 
schema: 2.0.0
title: Enable-OdbcPerfCounter
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: CBE7F5BF-3E8F-423F-B499-A59B783C56A4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-OdbcPerfCounter

## SYNOPSIS
Enables connection pooling Performance Monitor counters.

## SYNTAX

### InputObject (Default)
```
Enable-OdbcPerfCounter [-PassThru] [-InputObject] <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Platform
```
Enable-OdbcPerfCounter [-PassThru] [[-Platform] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-OdbcPerfCounter** cmdlet enables the Open Database Connectivity (ODBC) connection pooling Performance Monitor counters for troubleshooting ODBC connection pooling.

For more information about ODBC and performance counters, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) and [ODBC Performance Counters](https://msdn.microsoft.com/en-us/library/windows/desktop/ms709288.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Enable Performance Counter on a 32-bit platform
```
PS C:\> Enable-OdbcPerfCounter -Platform "32-bit"
```

This command enables the ODBC Performance Counter setting on a 32-bit platform.

### Example 2: Enable Performance Counter on both platforms
```
PS C:\> Enable-OdbcPerfCounter -Platform "All"
```

This command enables the ODBC Performance Counter setting on both 32-bit and 64-bit platforms.

### Example 3: Enable and disable Performance Counter on a 32-bit platform
```
PS C:\> $perfCounter = Enable-OdbcPerfCounter -Platform "32-bit" -PassThru
PS C:\> Disable-OdbcPerfCounter -InputObject $perfCounter
```

This command first enables the ODBC Performance Counter setting on 32-bit platform, and then stores the result in the **$perfCounter** variable.
After you run the first command, you can run ODBC applications that use pooling.
The second command disables the ODBC Performance Counter setting specified by **$perfCounter**.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Specifies an array of input objects.
This cmdlet enables the ODBC connection pooling Performance Monitor counters that the specified objects represent.
Specify a variable that contains the objects, or type a command or expression that gets the objects.

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
This cmdlet enables the ODBC connection pooling Performance Monitor counters that belong to the architecture that the parameter specifies.
The acceptable values for this parameter are:

- 32-bit
- 64-bit
- All

The default value is 32-bit on a 32-bit process.
The default value is 64-bit on a 64-bit process.
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
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcPerfCounter[]

## NOTES

## RELATED LINKS

[Disable-OdbcPerfCounter](./Disable-OdbcPerfCounter.md)

[Get-OdbcPerfCounter](./Get-OdbcPerfCounter.md)



---
external help file: WDAC_Cmdlets.xml
Module Name: Wdac
online version: https://docs.microsoft.com/powershell/module/wdac/enable-odbcperfcounter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-OdbcPerfCounter

## SYNOPSIS
Enables the ODBC connection pooling Performance Monitor counters for troubleshooting ODBC connection pooling.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-OdbcPerfCounter [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-OdbcPerfCounter [[-Platform] <String>] [-AsJob] [-CimSession <CimSession>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
For more information about ODBC and performance counters, see Microsoft Open Database Connectivity (ODBC)https://msdn.microsoft.com/en-us/library/ms710252.aspx and ODBC Performance Countershttps://msdn.microsoft.com/en-us/library/windows/desktop/ms709288.aspx.

## EXAMPLES

### 1:
```
PS C:\> Enable-OdbcPerfCounter -Platform 32-bit
```

Enable the ODBC Performance Counter setting on 32-bit platform:

### 2:
```
PS C:\> Enable-OdbcPerfCounter -Platform All
```

Enable the ODBC Performance Counter setting on both 32-bit and 64-bit platform:

### 3:
```
PS C:\> $perfCounter = Enable-OdbcPerfCounter -Platform 32-bit -PassThru
<Execute some ODBC applications that are using ODBC pooling>
Disable-OdbcPerfCounter $perfCounter
```

This command first enables the ODBC Performance Counter setting on 32-bit platform.
It also saves the result into a PowerShell variable that can be reused in Disable-OdbcPerfCounter:

## PARAMETERS

### -InputObject
Enables the ODBC Connection Pooling PerfMon counters represented by the specified ODBC PerfMon counters objects.
Enter a variable that contains the objects, or type a command or expression that gets the objects.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Platform
The platform architecture of the ODBC Connection Pooling PerfMon counters.
Possible values are '32-bit', '64-bit' or 'All'.
The default is '32-bit' on a 32-bit process and '64-bit' on a 64-bit process.
This is the platform architecture on the remote machine if this command is executed on a remote CIM session.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Passes the object created by this cmdlet through the pipeline.
By default, this cmdlet does not pass any objects through the pipeline.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcPerfCounter[]

## NOTES

## RELATED LINKS

[Disable-OdbcPerfCounter](./Disable-OdbcPerfCounter.md)

[Get-OdbcPerfCounter](./Get-OdbcPerfCounter.md)




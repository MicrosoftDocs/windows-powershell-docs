---
external help file: WDAC_Cmdlets.xml
Module Name: Wdac
online version: https://docs.microsoft.com/powershell/module/wdac/get-odbcperfcounter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-OdbcPerfCounter

## SYNOPSIS
Retrieves the ODBC connection pooling Performance Monitor counters.

## SYNTAX

```
Get-OdbcPerfCounter [[-Platform] <String>] [-AsJob] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
For more information about ODBC and performance counters, see Microsoft Open Database Connectivity (ODBC)https://msdn.microsoft.com/en-us/library/ms710252.aspx and ODBC Performance Countershttps://msdn.microsoft.com/en-us/library/windows/desktop/ms709288.aspx.

## EXAMPLES

### 1:
```
PS C:\> Get-OdbcPerfCounter -Platform 32-bit
```

Obtain the ODBC Performance Counter setting on 32-bit platform:

### 2:
```
PS C:\> Get-OdbcPerfCounter
```

Obtain the ODBC Performance Counter setting on both 32-bit and 64-bit platform:

### 3:
```
PS C:\> $perfCounter = Get-OdbcPerfCounter -Platform 32-bit
```

Obtain the ODBC Performance Counter setting on 32-bit platform and stores the result into a PowerShell variable:

## PARAMETERS

### -Platform
The platform architecture of the ODBC connection pooling PerfMon counters to get.
Possible values are '32-bit', '64-bit' or 'All'.
The default is 'All'.
This is the platform architecture on the remote machine if this command is executed on a remote CIM session.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcPerfCounter[]

## NOTES

## RELATED LINKS

[Disable-OdbcPerfCounter](./Disable-OdbcPerfCounter.md)

[Enable-OdbcPerfCounter](./Enable-OdbcPerfCounter.md)




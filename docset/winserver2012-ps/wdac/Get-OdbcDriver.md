---
external help file: WDAC_Cmdlets.xml
Module Name: Wdac
online version: https://docs.microsoft.com/powershell/module/wdac/get-odbcdriver?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-OdbcDriver

## SYNOPSIS
Retrieves one or more installed ODBC drivers from the system that match the value passed to the Name and Platform parameters.
If the Name parameter is not specified, the default is to match all driver names.
If no parameters are provided, retrieves all ODBC drivers installed on the system.

## SYNTAX

```
Get-OdbcDriver [[-Name] <String>] [-AsJob] [-CimSession <CimSession>] [-Platform <String>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
For more information about ODBC and drivers, see Microsoft Open Database Connectivity (ODBC)http://msdn.microsoft.com/en-us/library/ms710252.aspx and Drivershttp://msdn.microsoft.com/en-us/library/ms715383.aspx.

## EXAMPLES

### 1:
```
PS C:\> Get-OdbcDriver
```

This command gets all installed ODBC drivers (both 32-bit and 64-bit):

### 2:
```
PS C:\> Get-OdbcDriver "SQL Server Native Client 10.0" -Platform 32-bit
```

This command gets the driver named as "SQL Server Native Client 10.0" on the 32-bit platform:

### 3:
```
PS C:\> Get-OdbcDriver -Name "SQL Server*" -Platform 64-bit
```

This command gets all installed ODBC drivers with name beginning with "SQL Server" under the 64-bit platform:

### 4:
```
PS C:\> $driverArray = Get-OdbcDriver
```

This command is similar to Example 1, but it saves the outputted driver object into a PowerShell variable for future use:

## PARAMETERS

### -Name
Specifies one or more ODBC drivers by driver name.
You can use wildcard characters.
The default is to return all ODBC drivers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Platform
The platform architecture of the ODBC driver.
Possible values are '32-bit', '64-bit' or 'All'.
The default is 'All'.
This is the platform architecture on the remote machine if this command is executed in a remote CIM session.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDriver[]

## NOTES

## RELATED LINKS

[Set-OdbcDriver](./Set-OdbcDriver.md)




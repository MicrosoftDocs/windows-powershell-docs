---
external help file: WDAC_Cmdlets.xml
Module Name: Wdac
online version: https://learn.microsoft.com/powershell/module/wdac/get-odbcdsn?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-OdbcDsn

## SYNOPSIS
Retrieves one or more ODBC data source names (DSNs) from the system that match the value passed to the Name, DsnType, Platform, and DriverName parameters.
If the Name or DriverName parameter is not specified, the default is to match all DSN names and all driver names respectively.
If no parameters are provided, retrieves all ODBC DSNs from the system.

## SYNTAX

```
Get-OdbcDsn [[-Name] <String>] [-AsJob] [-CimSession <CimSession>] [-DriverName <String>] [-DsnType <String>]
 [-Platform <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
For more information about ODBC, data source names, and drivers, see Microsoft Open Database Connectivity (ODBC)http://msdn.microsoft.com/en-us/library/ms710252.aspx, Data Sourceshttp://msdn.microsoft.com/en-us/library/ms711688.aspx, and Drivershttp://msdn.microsoft.com/en-us/library/ms715383.aspx.

## EXAMPLES

### 1:
```
PS C:\> Get-OdbcDsn
```

This command gets all ODBC User DSN(s) and System DSN(s) that are using 32-bit or 64-bit ODBC drivers:

### 2:
```
PS C:\> Get-OdbcDsn "MyPayroll" -DsnType System -Platform 32-bit
```

This command gets the ODBC System DSN(s) named as "MyPayroll" which is stored in the 32-bit registry location.
The Name parameter is positioned at 0:

### 3:
```
PS C:\> Get-OdbcDsn -Name "*Payroll*"
```

This command gets all ODBC User DSN(s) and System DSN(s) with name matches the wildcard and which is stored in the native hive of the registry location:

### 4:
```
PS C:\> $dsnArray = Get-OdbcDsn -DriverName "SQL Server*"
```

This command gets all ODBC User DSN(s) that is using a driver with a name matching the above wildcard.
It also saves the result into a PowerShell variable for future use:

## PARAMETERS

### -Name
Specifies one or more ODBC DSNs by DSN name.
You can use wildcard characters.
The default is to return all ODBC DSNs.

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

### -DsnType
The type of the ODBC DSN to retrieve.
Possible values are 'User', 'System' or 'All'.
The default is 'All'.

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

### -Platform
The platform architecture of the ODBC DSN to retrieve.
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

### -DriverName
Gets only ODBC DSNs that are using the specified ODBC driver.
You can use wildcard characters.
The default is to return all ODBC DSNs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDsn[]

## NOTES

## RELATED LINKS

[Add-OdbcDsn](./Add-OdbcDsn.md)

[Remove-OdbcDsn](./Remove-OdbcDsn.md)

[Set-OdbcDsn](./Set-OdbcDsn.md)




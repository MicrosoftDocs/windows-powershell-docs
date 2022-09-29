---
external help file: WDAC_Cmdlets.xml
Module Name: Wdac
online version: https://learn.microsoft.com/powershell/module/wdac/add-odbcdsn?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-OdbcDsn

## SYNOPSIS
Adds an ODBC data source name into the system.

## SYNTAX

```
Add-OdbcDsn [-Name] <String> [-AsJob] [-CimSession <CimSession>] [-PassThru] [-Platform <String>]
 [-SetPropertyValue <String>] [-ThrottleLimit <Int32>] -DriverName <String> -DsnType <String>
```

## DESCRIPTION
Add-OdbcDsn adds an ODBC DSN into the system.
You can specify the properties of the new DSN with the parameter SetPropertyValue.

Do not attempt to use Set-OdbcDsn to add a new DSN.

For more information about ODBC, data source names, and drivers, see Microsoft Open Database Connectivity (ODBC)http://msdn.microsoft.com/en-us/library/ms710252.aspx, Data Sourceshttp://msdn.microsoft.com/en-us/library/ms711688.aspx, and Drivershttp://msdn.microsoft.com/en-us/library/ms715383.aspx.

## EXAMPLES

### 1:
```
PS C:\> Add-OdbcDsn MyPayroll -DriverName "Microsoft Access Driver (*.mdb, *.accdb)" -DsnType User -Platform 32-bit -SetPropertyValue 'Dbq=C:\mydatabase.accdb'
```

This command adds a 32-bit ODBC User DSN named as "MyPayroll" using the specified 32-bit driver "Microsoft Access Driver (*.mdb, *.accdb)" with the specified DBQ properties.
The Name parameter is positioned at 0:

### 2:
```
PS C:\> Add-OdbcDsn MyPayroll -DriverName "SQL Server Native Client 10.0" -DsnType System -SetPropertyValue @("Server=MyServer", "Trusted_Connection=Yes", "Database=Payroll")
```

This command adds the ODBC System DSN(s) named as "MyPayroll" using SQL Server Native Client 10.0 with the specified DSN properties.
Note that Platform defaults to the native platform:

### 3:
```
PS C:\> $newDsn = Add-OdbcDsn MyPayroll -DriverName "SQL Server Native Client 10.0" -DsnType System -SetPropertyValue @("Server=MyServer", "Trusted_Connection=Yes", "Database=Payroll") -PassThru
```

This command is equivalent to example 2, but it saves the newly-created System DSN object into a PowerShell variable for future use.
By default, this command does not return the driver object if the "PassThru" parameter is not specified:

### 4:
```
C:\PS> $dsnArr = Get-OdbcDsn -DriverName 'SQL Server Native Client 10.0'
C:\PS> foreach ($dsn in $dsnArr) {
          Remove-OdbcDsn $dsn 
          # You can change the property array as well, 
          # if DSN attributes have been changed in the new driver version

          Add-OdbcDsn -Name $dsn.Name -DsnType $dsn.DsnType -Platform $dsn.Platform -DriverName 'SQL Server Native Client 12.0' -SetPropertyValue $dsn.PropertyValue
}
```

This command migrates DSNs using the SQL Server Native Client 10.0 driver to a newer version of that driver.
This command works for the SQL Server Native Client ODBC driver.

## PARAMETERS

### -Name
The name of the ODBC DSN to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DsnType
The type of the ODBC DSN to add.
Possible values are 'User' or 'System'.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Platform
The platform architecture of the ODBC DSN you are adding.
Possible values are '32-bit' or '64-bit'.
The default is '32-bit' on a 32-bit process and '64-bit' on a 64-bit process.
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
The name of the ODBC driver for the new ODBC DSN.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SetPropertyValue
Specifies the property values of the new ODBC DSN.
Format as an array of strings where each string is: \<key\>=\<value\>.

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

[Get-OdbcDsn](./Get-OdbcDsn.md)

[Remove-OdbcDsn](./Remove-OdbcDsn.md)

[Set-OdbcDsn](./Set-OdbcDsn.md)




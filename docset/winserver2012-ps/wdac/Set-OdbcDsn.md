---
external help file: WDAC_Cmdlets.xml
Module Name: Wdac
online version: https://learn.microsoft.com/powershell/module/wdac/set-odbcdsn?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-OdbcDsn

## SYNOPSIS
Modifies one or more ODBC data source names (DSNs).
This modifies existing DSNs in the system.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-OdbcDsn [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-PassThru]
 [-RemovePropertyValue <String>] [-SetPropertyValue <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-OdbcDsn [-Name] <String> [-AsJob] [-CimSession <CimSession>] [-DriverName <String>] [-PassThru]
 [-Platform <String>] [-RemovePropertyValue <String>] [-SetPropertyValue <String>] [-ThrottleLimit <Int32>]
 -DsnType <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
Set-OdbcDsn configures the properties for one or more existing ODBC DSNs.
You can specify the properties to add or modify with the parameter SetPropertyValue, and specify the properties to remove with the parameter RemovePropertyValue.

Use Add-OdbcDsn to add a new DSN.

For more information about ODBC, data source names, and drivers, see Microsoft Open Database Connectivity (ODBC)http://msdn.microsoft.com/en-us/library/ms710252.aspx, Data Sourceshttp://msdn.microsoft.com/en-us/library/ms711688.aspx, and Drivershttp://msdn.microsoft.com/en-us/library/ms715383.aspx.

## EXAMPLES

### 1:
```
PS C:\> Set-OdbcDsn -Name "MyPayroll" -DsnType System -Platform 64-bit -SetPropertyValue "Database=Payroll"
```

This command changes the 64-bit ODBC System DSN named "MyPayroll" to use a database named as "Payroll".
This example is designed for SQL Server drivers:

### 2:
```
PS C:\> Set-OdbcDsn MyPayroll -DsnType System -SetPropertyValue "Database=Payroll"
```

This command is similar to the previous example, but it configures a DSN on the native platform, which is the default Platform value:

### 3:
```
PS C:\> Set-OdbcDsn -Name "MyPayroll" -DsnType User -Platform 32-bit -RemovePropertyValue @("UID", "PWD") -SetPropertyValue @("Trusted_Connection=Yes", "Database=Payroll")
```

This command changes the specified 32-bit ODBC User DSN with name equal to "MyPayroll" from using SQL Server Authentication to using Windows Authentication.
(This example is designed for SQL Server drivers.) Also, it sets the Database key to "Payroll":

### 4:
```
PS C:\> Set-OdbcDsn -Name "*Payroll*" -DsnType All -Platform All -DriverName "Microsoft Access Driver (*.mdb, *.accdb)" -SetPropertyValue 'Dbq=C:\payroll.accdb'
```

This command changes all ODBC User DSN(s) and System DSN(s) on both platforms with name matching the wildcard "*Payroll*" and that is using a driver named "Microsoft Access Driver (*.mdb, *.accdb)" to use the database file "C:\payroll.accdb":

### 5:
```
PS C:\> Get-OdbcDsn -DriverName "SQL Server*" -DsnType All -Platform All
| Where-Object{ ($_.Attribute["Server"] -eq "oldServer") }
| Set-OdbcDsn -SetPropertyValue "Server=newServer"
```

This command migrates the oldServer to newServer for all User DSN(s) and System DSN(s) using a driver with name started with "SQL Server":

### 6:
```
PS C:\> $sysDsn = Set-OdbcDsn "MyPayroll" -DsnType System -Platform All -SetPropertyValue "Database=Payroll" -PassThru
```

This command is equivalent to the first example but it also stores the output object in a PowerShell variable.
By default, this command does not return the driver object if the "PassThru" parameter is not specified:

### 7:
```
PS C:\> $dsnArray = Get-OdbcDsn -DriverName "SQL Server*" | Where-Object{ ($_.Attribute["Server"] -eq "oldServer") }
Set-OdbcDsn $dsnArray -SetPropertyValue "Server=newServer"
```

This command migrates the oldServer to newServer for all User DSN(s) and System DSN(s) using a driver with name started with "SQL Server" and uses the PowerShell variable $dsnArray.

## PARAMETERS

### -InputObject
Modifies the ODBC DSNs represented by the specified ODBC DSN objects.
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

### -Name
The name of the ODBC DSN to set.
You can use wildcard characters.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -DsnType
The type of the ODBC DSN to set.
Possible values are 'User', 'System' or 'All'.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Platform
The platform architecture of the ODBC DSN to set.
Possible values are '32-bit', '64-bit' or 'All'.
The default is '32-bit' on a 32-bit process and '64-bit' on a 64-bit process.
This is the platform architecture on the remote machine if this command is executed in a remote CIM session.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DriverName
This cmdlet will set the ODBC DSN using this driver only.
You can use wildcard characters.
The default is to set all ODBC DSNs.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -SetPropertyValue
Specifies the property values of the ODBC DSN that you are modifying or adding.
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

### -RemovePropertyValue
Specifies the property values of the ODBC DSN to be deleted.
This is an array of keys to be removed.

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
Passes the object modified by this cmdlet through the pipeline.
By default, this cmdlet does not pass any objects through the pipeline.

Returns an object representing the set content.
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDsn[]

## NOTES

## RELATED LINKS

[Add-OdbcDsn](./Add-OdbcDsn.md)

[Get-OdbcDsn](./Get-OdbcDsn.md)

[Remove-OdbcDsn](./Remove-OdbcDsn.md)




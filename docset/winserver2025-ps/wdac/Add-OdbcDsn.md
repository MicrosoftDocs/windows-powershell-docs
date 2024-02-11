---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_OdbcDsnTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/add-odbcdsn?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-OdbcDsn
---

# Add-OdbcDsn

## SYNOPSIS
Adds an ODBC DSN.

## SYNTAX

```
Add-OdbcDsn [-Name] <String> -DriverName <String> [-SetPropertyValue <String[]>] [-PassThru]
 [-Platform <String>] -DsnType <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-OdbcDsn** cmdlet adds an Open Database Connectivity (ODBC) data source name (DSN) to the computer.
You can specify the properties of the DSN by using the *SetPropertyValue* parameter.

Do not use the Set-OdbcDsn cmdlet to add a new DSN.

For more information about ODBC, data source names, and drivers, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx), [Data Sources](https://msdn.microsoft.com/en-us/library/ms711688.aspx), and [Drivers](https://msdn.microsoft.com/en-us/library/ms715383.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Add a 32-bit ODBC User DSN
```
PS C:\> Add-OdbcDsn -Name "MyPayroll" -DriverName "Microsoft Access Driver (*.mdb, *.accdb)" -DsnType "User" -Platform "32-bit" -SetPropertyValue 'Dbq=C:\mydatabase.accdb'
```

This command adds a 32-bit ODBC User DSN named MyPayroll that uses the specified 32-bit driver with the specified properties.

### Example 2: Add an ODBC System DSN
```
PS C:\> Add-OdbcDsn -Name "MyPayroll" -DriverName "SQL Server Native Client 10.0" -DsnType "System" -SetPropertyValue @("Server=MyServer", "Trusted_Connection=Yes", "Database=Payroll")
```

This command adds the ODBC System DSNs named MyPayroll that use SQL Server Native Client 10.0 with the specified DSN properties.
Because the command does not include the *Platform* parameter, the platform architecture is the default, native platform.

### Example 3: Add and store an ODBC System DSN
```
PS C:\> $NewDsn = Add-OdbcDsn -Name "MyPayroll" -DriverName "SQL Server Native Client 10.0" -DsnType "System" -SetPropertyValue @("Server=MyServer", "Trusted_Connection=Yes", "Database=Payroll") -PassThru
```

This command adds the ODBC System DSNs named MyPayroll that use SQL Server Native Client 10.0 with the specified DSN properties, and then stores the results in the $NewDsn variable.
The command includes the *PassThru* parameter.
Without *PassThru*, the cmdlet does not return anything.

### Example 4: Migrates DSNs to a newer version of a driver
```
PS C:\> $DsnArray = Get-OdbcDsn -DriverName 'SQL Server Native Client 10.0'
PS C:\> ForEach ($Dsn in $ DsnArray) {
          Remove-OdbcDsn -InputObject $Dsn
          # You can change the property array as well,
          # if DSN attributes have been changed in the new driver version

PS C:\> Add-OdbcDsn -Name $Dsn.Name -DsnType $Dsn.DsnType -Platform $Dsn.Platform -DriverName 'SQL Server Native Client 12.0' -SetPropertyValue $Dsn.PropertyValue
}
```

The first command gets ODBC data source names by using the Get-OdbcDsn cmdlet, and then stores them in the $DsnArray variable.

The second command uses the ForEach Windows PowerShell keyword to step through each member of $DsnArray.
For each member, the command uses the current cmdlet to migrate DSNs using the SQL Server Native Client 10.0 driver to a newer version of that driver.
This command works for the SQL Server Native Client ODBC driver.

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

### -DriverName
Specifies the name of a driver.
This cmdlet assigns the new ODBC DSN to the driver that this parameter specifies.

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

### -DsnType
Specifies the type of an ODBC DSN.
This cmdlet adds a DSN of the type that this parameter specifies.
The acceptable values for this parameter are:

- User
- System

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: User, System

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an ODBC DSN.
This cmdlet creates a DSN that has the name that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DsnName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet adds an ODBC DSN that belongs to the platform that this parameter specifies.
The acceptable values for this parameter are:

- 32-bit
- 64-bit

The default value is 32-bit on a 32-bit process.
The default value is 64-bit on a 64-bit process.
If you run this cmdlet in a remote Common Information Model (CIM) session, this parameter refers to the platform architecture on the remote computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: 32-bit, 64-bit

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SetPropertyValue
Specifies an array of property values.
This cmdlet specifies these property values for the ODBC DSN.
Specify an array of strings of the form \<key\>=\<value\>.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDsn[]

## NOTES

## RELATED LINKS

[Get-OdbcDsn](./Get-OdbcDsn.md)

[Remove-OdbcDsn](./Remove-OdbcDsn.md)

[Set-OdbcDsn](./Set-OdbcDsn.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_OdbcDsnTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/set-odbcdsn?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-OdbcDsn
---

# Set-OdbcDsn

## SYNOPSIS
Configures properties for existing ODBC DSNs.

## SYNTAX

### InputObject (Default)
```
Set-OdbcDsn [-PassThru] [-SetPropertyValue <String[]>] [-RemovePropertyValue <String[]>]
 [-InputObject] <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Name
```
Set-OdbcDsn [-PassThru] [-SetPropertyValue <String[]>] [-RemovePropertyValue <String[]>] [-Name] <String>
 [-DriverName <String>] [-Platform <String>] -DsnType <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-OdbcDsn** cmdlet configures the properties for existing Open Database Connectivity (ODBC) data source names (DSNs).
Specify properties to add or modify by using the *SetPropertyValue* parameter.
Specify properties to remove by using the *RemovePropertyValue* parameter.

Use the Add-OdbcDsn cmdlet to add a new DSN.

For more information about ODBC, data source names, and drivers, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx), [Data Sources](https://msdn.microsoft.com/en-us/library/ms711688.aspx), and [Drivers](https://msdn.microsoft.com/en-us/library/ms715383.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Change a 64-bit ODBC DSN to use a specified database
```
PS C:\> Set-OdbcDsn -Name "MyPayroll" -DsnType "System" -Platform "64-bit" -SetPropertyValue "Database=Payroll"
```

This command changes the 64-bit ODBC System DSN named MyPayroll to use a database named Payroll.
This example is designed for SQL Server drivers.

### Example 2: Change a native platform ODBC DSN to use a specified database
```
PS C:\> Set-OdbcDsn -Name "MyPayroll" -DsnType "System" -SetPropertyValue "Database=Payroll"
```

This command changes the native platform ODBC System DSN named MyPayroll to use a database named Payroll.
This example resembles the previous example, but it does not specify the *Platform* parameter.Therefore, configures a DSN on the native platform.

### Example 3: Change a User DSN to use Windows Authentication and a specified database
```
PS C:\> Set-OdbcDsn -Name "MyPayroll" -DsnType "User" -Platform "32-bit" -RemovePropertyValue @("UID", "PWD") -SetPropertyValue @("Trusted_Connection=Yes", "Database=Payroll")
```

This command changes the specified 32-bit ODBC User DSN named MyPayroll from using SQL Server Authentication to using Windows Authentication.
This example is designed for SQL Server drivers.
Also, the command specifies a value of Payroll for the Database key.

### Example 4: Change specified DSNs to use a specified database file
```
PS C:\> Set-OdbcDsn -Name "*Payroll*" -DsnType "All" -Platform "All" -DriverName "Microsoft Access Driver (*.mdb, *.accdb)" -SetPropertyValue 'Dbq=C:\payroll.accdb'
```

This command changes all ODBC User DSNs and System DSNs on both platforms with names that contain Payroll and that use a driver named Microsoft Access Driver (*.mdb, *.accdb) to use the database file C:\payroll.accdb.

### Example 5: Migrate all DSNs that use a driver with name that starts with a string
```
PS C:\> Get-OdbcDsn -DriverName "SQL Server*" -DsnType "All" -Platform "All" | Where-Object{ ($_.Attribute["Server"] -eq "oldServer") } | Set-OdbcDsn -SetPropertyValue "Server=newServer"
```

This command migrates the oldServer to newServer for all User DSNs and System DSNs that use a driver that has a name that starts with SQL Server.

### Example 6: Change a 64-bit ODBC System DSN to use a specified database
```
PS C:\> $sysDsn = Set-OdbcDsn -Name "MyPayroll" -DsnType "System" -Platform "All" -SetPropertyValue "Database=Payroll" -PassThru
```

This command changes the 64-bit ODBC System DSN named MyPayroll to use a database named Payroll, and then stores the result in the $sysDsn variable.
The command includes the *PassThru* parameter.
Without *PassThru*, the cmdlet does not return anything.

### Example 7: Migrates DSNs that use a driver with name that starts with a string by using a variable
```
PS C:\> $DsnArray = Get-OdbcDsn -DriverName "SQL Server*" | Where-Object{ ($_.Attribute["Server"] -eq "oldServer") }
PS C:\> Set-OdbcDsn -InputObject $DsnArray -SetPropertyValue "Server=newServer"
```

The first command uses the Get-OdbcDsn cmdlet to get each driver that has a name that starts with SQL Server and has a value of oldServer for the **Server** attribute.
The command stores the results in the $DsnArray variable.

The second command sets the value for **Server** to a new value.

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

### -DriverName
Specifies the name of a driver.
This cmdlet modifies the ODBC DSN that uses the driver that this parameter specifies.
You can use wildcard characters.
If you do not specify this parameter, this cmdlet modifies DSNs for all drivers.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DsnType
Specifies the type of an ODBC DSN.
This cmdlet modifies a DSN of the type that this parameter specifies.
The acceptable values for this parameter are:

- User
- System
- All

```yaml
Type: String
Parameter Sets: Name
Aliases:
Accepted values: User, System, All

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject
Aliases: Dsn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of an ODBC DSN.
This cmdlet modifies the DSN that this parameter specifies.
You can use wildcard characters to specify more than one ODBC DSN.

```yaml
Type: String
Parameter Sets: Name
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
This cmdlet modifies the ODBC DSN that belongs to the architecture that this parameter specifies.
The acceptable values for this parameter are:

- 32-bit
- 64-bit
- All

The default value is 32-bit on a 32-bit process.
The default value is 64-bit on a 64-bit process.
If you run this cmdlet in a remote CIM session, this parameter refers to the platform architecture on the remote computer.

```yaml
Type: String
Parameter Sets: Name
Aliases:
Accepted values: 32-bit, 64-bit, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemovePropertyValue
Specifies an array of property values to remove.
This cmdlet removes the property values that this parameter specifies from the ODBC DSN.
Specify an array of keys to remove.

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

### -SetPropertyValue
Specifies an array of property values.
This cmdlet modifies the properties that this parameter specifies for the ODBC DSN.
Specify array of strings of the form \<key\>=\<value\>.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDsn[]

## NOTES

## RELATED LINKS

[Add-OdbcDsn](./Add-OdbcDsn.md)

[Get-OdbcDsn](./Get-OdbcDsn.md)

[Remove-OdbcDsn](./Remove-OdbcDsn.md)


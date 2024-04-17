---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_OdbcDsnTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/remove-odbcdsn?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-OdbcDsn
---

# Remove-OdbcDsn

## SYNOPSIS
Removes ODBC DSNs.

## SYNTAX

### InputObject (Default)
```
Remove-OdbcDsn [-PassThru] [-InputObject] <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name
```
Remove-OdbcDsn [-PassThru] [-Name] <String> [-DriverName <String>] [-Platform <String>] -DsnType <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-OdbcDsn** cmdlet removes Open Database Connectivity (ODBC) data source names (DSNs) from the computer.

For more information about ODBC, data source names, and drivers, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx), [Data Sources](https://msdn.microsoft.com/en-us/library/ms711688.aspx), and [Drivers](https://msdn.microsoft.com/en-us/library/ms715383.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Remove 32-bit User DSNs that have names that contain a string
```
PS C:\> Remove-OdbcDsn -Name "*Payroll*" -DsnType "User" -Platform "32-bit"
```

This command removes the 32-bit ODBC User DSNs that have names that contain Payroll.

### Example 2: Remove the System DSN named MyPayroll from the native platform
```
PS C:\> Remove-OdbcDsn -Name "MyPayroll" -DsnType "System"
```

This command removes the ODBC System DSN named MyPayroll from the native platform.

### Example 3: Remove all 32-bit ODBC System DSNs by using wildcard characters
```
PS C:\> Remove-OdbcDsn -Name "*Payroll*" -DsnType "System" -Platform "32-bit" -DriverName "SQL Server*"
```

This command removes all 32-bit ODBC System DSNs that have names that contain the string *Payroll*, and use the driver that has a name that starts with SQL Server.

### Example 4: Remove a 32-bit ODBC User DSN by using a name
```
PS C:\> $SysDsn = Remove-OdbcDsn -Name "MyPayroll" -DsnType "User" -Platform "32-bit" -PassThru
```

This command removes the 32-bit ODBC User DSNs named MyPayroll, and then stores the deleted DSN object in the $SysDsn variable.

### Example 5: Remove a System DSN on the native platform by using the pipeline operator
```
PS C:\> Get-OdbcDsn -Name "MyPayroll" -DsnType "System" | Remove-OdbcDsn
```

This command uses the Get-OdbcDsn to get the ODBC System DSN on the native platform named MyPayroll, and then passes it to the current cmdlet by using the pipeline operator.
The example removes that DSN.

### Example 6: Remove a ODBC System DSN on the native platform by using a variable
```
PS C:\> $DsnArray = Get-OdbcDsn -Name "MyPayroll" -DsnType "System"
PS C:\> Remove-OdbcDsn -InputObject $DsnArray
```

The first command uses Get-OdbcDsn to get the ODBC System DSN on the native platform named MyPayroll, and then stores it in the $DsnArray variable.

The second command removes the DSN stored in $DsnArray.

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
This cmdlet removes the ODBC DSN that uses the driver that this parameter specifies.
You can use wildcard characters.
If you do not specify this parameter, this cmdlet removes DSNs for all drivers.

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
This cmdlet removes DSNs of the type that this parameter specifies.
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
Specifies the name of an ODBC DSNs.
You can use wildcard characters to specify more than one name.
This cmdlet removes the DSNs that the names specify.

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
This cmdlet removes the ODBC DSNs that belong to the architecture that this parameter specifies.
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

[Set-OdbcDsn](./Set-OdbcDsn.md)


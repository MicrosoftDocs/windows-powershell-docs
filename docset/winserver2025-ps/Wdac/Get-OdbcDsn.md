---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_OdbcDsnTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/get-odbcdsn?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OdbcDsn
---

# Get-OdbcDsn

## SYNOPSIS
Gets ODBC DSNs.

## SYNTAX

```
Get-OdbcDsn [[-Name] <String>] [-DriverName <String>] [-Platform <String>] [-DsnType <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-OdbcDsn** cmdlet gets Open Database Connectivity (ODBC) data source names (DSNs) from the computer.
You can specify values for the *Name*, *DsnType*, *Platform*, and *DriverName* parameters.
If you do not specify *Name* or *DriverName*, the cmdlet gets all DSN names and all driver names respectively.
If you do not specify any parameter, the cmdlet gets all ODBC DSNs from the computer.

For more information about ODBC, data source names, and drivers, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx), [Data Sources](https://msdn.microsoft.com/en-us/library/ms711688.aspx), and [Drivers](https://msdn.microsoft.com/en-us/library/ms715383.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Get all DSNs
```
PS C:\> Get-OdbcDsn
```

This command gets all ODBC User DSNs and System DSNs that use 32-bit or 64-bit ODBC drivers.

### Example 2: Get ODBC System DSNs by name
```
PS C:\> Get-OdbcDsn -Name "MyPayroll" -DsnType "System" -Platform "32-bit"
```

This command gets the ODBC System DSNs named MyPayroll stored in the 32-bit registry location.

### Example 3: Get ODBC DSNs with names that contain a string
```
PS C:\> Get-OdbcDsn -Name "*Payroll*"
```

This command gets all ODBC User DSNs and System DSNs with names that contain the string Payroll.
The DSNs are stored in the native hive of the registry location.

### Example 4: Get all ODBC User DSNs for specified driver
```
PS C:\> $DsnArray = Get-OdbcDsn -DriverName "SQL Server*"
```

This command gets all ODBC User DSNs that use a driver that has the specified name, and then stores those DSN in the $DsnArray variable.

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
This cmdlet gets ODBC DSNs that use the specified ODBC driver.
You can use wildcard characters.
If you do not specify this parameter, this cmdlet gets all ODBC DSNs.

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

### -DsnType
Specifies the type of an ODBC DSN.
This cmdlet gets DSNs of the type that this parameter specifies.
The acceptable values for this parameter are:

- User
- System
- All

The default value is All.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: User, System, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an ODBC DSN.
You can use wildcard characters to specify more than one ODBC DSN.
If you do not specify this parameter, this cmdlet returns all ODBC DSNs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DsnName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Platform
Specifies the platform architecture.
This cmdlet gets the ODBC DSN that belong to the architecture that this parameter specifies.
The acceptable values for this parameter are:

- 32-bit
- 64-bit
- All

The default value is All.
If you run this cmdlet in a remote CIM session, this parameter refers to the platform architecture on the remote computer.

```yaml
Type: String
Parameter Sets: (All)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDsn[]

## NOTES

## RELATED LINKS

[Add-OdbcDsn](./Add-OdbcDsn.md)

[Remove-OdbcDsn](./Remove-OdbcDsn.md)

[Set-OdbcDsn](./Set-OdbcDsn.md)


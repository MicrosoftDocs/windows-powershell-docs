---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_OdbcDriverTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/get-odbcdriver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OdbcDriver
---

# Get-OdbcDriver

## SYNOPSIS
Gets installed ODBC drivers.

## SYNTAX

```
Get-OdbcDriver [[-Name] <String>] [-Platform <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-OdbcDriver** cmdlet gets installed Open Database Connectivity (ODBC) drivers from the computer.
Specify values for the **Name** and **Platform** parameters.
If you do not specify a value for **Name**, the cmdlet gets drivers that have any driver name.
If you do not specify any parameters, the cmdlet gets all ODBC drivers installed on the computer.

For more information about ODBC and drivers, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) and [Drivers](https://msdn.microsoft.com/en-us/library/ms715383.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Get all installed ODBC drivers
```
PS C:\> Get-OdbcDriver
```

This command gets all installed ODBC drivers.
The cmdlet gets both 32-bit and 64-bit drivers.

### Example 2: Get a driver on the 32-bit platform by using a name
```
PS C:\> Get-OdbcDriver -Name "SQL Server Native Client 10.0" -Platform "32-bit"
```

This command gets the driver named SQL Server Native Client 10.0 on the 32-bit platform.

### Example 3: Get ODBC drivers that begin with a specified string on the 64-bit platform
```
PS C:\> Get-OdbcDriver -Name "SQL Server*" -Platform "64-bit"
```

This command gets installed ODBC drivers that have a name that starts with SQL Server on the 64-bit platform.

### Example 4: Get all ODBC drivers
```
PS C:\> $DriverArray = Get-OdbcDriver
```

This command gets all installed ODBC drivers, and then stores them in the $DriverArray variable for future use.

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

### -Name
Specifies the name of a driver.
You can use wildcard characters to specify more than one driver.
This cmdlet gets one or more ODBC drivers that this parameter specifies.
If you do not specify this parameter, this cmdlet gets all ODBC drivers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DriverName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Platform
Specifies the platform architecture.
This cmdlet gets ODBC drivers that belong to the architecture that this parameter specifies.
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDriver[]

## NOTES

## RELATED LINKS

[Set-OdbcDriver](./Set-OdbcDriver.md)


---
external help file: WDAC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 59C94EFA-A8D5-4695-833B-DA6075C4C549
manager: dansimp
---

# Remove-OdbcDsn

## SYNOPSIS
Removes one or more existing DSNs from the system.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-OdbcDsn [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-OdbcDsn [-Name] <String> [-AsJob] [-CimSession <CimSession>] [-DriverName <String>] [-PassThru]
 [-Platform <String>] [-ThrottleLimit <Int32>] -DsnType <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
For more information about ODBC, data source names, and drivers, see Microsoft Open Database Connectivity (ODBC)http://msdn.microsoft.com/en-us/library/ms710252.aspx, Data Sourceshttp://msdn.microsoft.com/en-us/library/ms711688.aspx, and Drivershttp://msdn.microsoft.com/en-us/library/ms715383.aspx.

## EXAMPLES

### 1:
```
PS C:\> Remove-OdbcDsn -Name "*Payroll*" -DsnType User -Platform 32-bit
```

This command removes the 32-bit ODBC User DSN(s) with a name matches the wildcard "*Payroll*":

### 2:
```
PS C:\> Remove-OdbcDsn "MyPayroll" -DsnType System
```

This command removes the ODBC System DSN with a name equal to "MyPayroll" from the native platform:

### 3:
```
PS C:\> Remove-OdbcDsn -Name "*Payroll*" -DsnType System -Platform 32-bit -DriverName "SQL Server*"
```

This command removes all 32-bit ODBC System DSN(s) that match the wildcard pattern "*Payroll*" and are using the driver with a name started with "SQL Server":

### 4:
```
PS C:\> $sysDsn = Remove-OdbcDsn "MyPayroll" -DsnType User -Platform 32-bit -PassThru
```

This command removes the 32-bit ODBC User DSN(s) with a name that matches the wildcard "*Payroll*" and stores the deleted DSN object into a PowerShell variable:

### 5:
```
PS C:\> Get-OdbcDsn -Name "MyPayroll" -DsnType System | Remove-OdbcDsn
```

This command removes the ODBC System DSN on the native platform with name equal to "MyPayroll" and pipelines the object returned from the command Get-OdbcDsn:

### 6:
```
PS C:\> $dsnArray = Get-OdbcDsn -Name "MyPayroll" -DsnType System
Remove-OdbcDsn $dsnArray
```

This command removes the ODBC System DSN on the native platform with name equal to "MyPayroll" and uses the PowerShell variable $dsnArray:

## PARAMETERS

### -InputObject
Removes the ODBC DSNs represented by the specified ODBC DSN objects.
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
Specifies one or more ODBC DSNs to remove.
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
The type of the ODBC DSN to remove.
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
The platform architecture of the ODBC DSN to remove.
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
This cmdlet will remove the ODBC DSN using this driver only.
You can use wildcard characters.
The default is to remove all ODBC DSNs.

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

### -PassThru
Passes the object removed by this cmdlet through the pipeline.
By default, this cmdlet does not pass any objects through the pipeline.

Returns an object representing the removed ODBC DSN(s).
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

[Set-OdbcDsn](./Set-OdbcDsn.md)




---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_OdbcDriverTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/set-odbcdriver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-OdbcDriver
---

# Set-OdbcDriver

## SYNOPSIS
Configures the properties for installed ODBC drivers.

## SYNTAX

### InputObject (Default)
```
Set-OdbcDriver [-PassThru] [-SetPropertyValue <String[]>] [-RemovePropertyValue <String[]>]
 [-InputObject] <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Name
```
Set-OdbcDriver [-PassThru] [-SetPropertyValue <String[]>] [-RemovePropertyValue <String[]>] [-Name] <String>
 [-Platform <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-OdbcDriver** cmdlet configures the properties for installed Open Database Connectivity (ODBC) drivers.
Specify properties to add or modify by using the *SetPropertyValue* parameter.
Specify properties to remove by using the *RemovePropertyValue* parameter.

Use the driver installation program to install and uninstall a driver.
You cannot install or uninstall a driver by using Windows PowerShell® cmdlets.

For more information about ODBC and drivers, see [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) and [Drivers](https://msdn.microsoft.com/en-us/library/ms715383.aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Assign a value for a 32-bit driver by using a name
```
PS C:\> Set-OdbcDriver -Name "SQL Server Native Client 10.0" -Platform "32-bit" -SetPropertyValue "CPTimeout=60"
```

This command assigns the key CPTimeout a value of 60 for the 32-bit driver named SQL Server Native Client 10.0.

### Example 2: Remove a property for any driver that starts with a string for the native platform
```
PS C:\> Set-OdbcDriver -Name "SQL Server*" -RemovePropertyValue "aaa"
```

This command removes the property named aaa for all drivers that have a name that starts with SQL Server under the native platform.

### Example 3: Change and remove properties for a driver
```
PS C:\> Set-OdbcDriver -Name "SQL Server Native Client 10.0" -Platform "All" -RemovePropertyValue @("aaa1", "aaa2") -SetPropertyValue @("aaa3=bbb3", "aaa4=bbb4")
```

This command operates on any driver named SQL Server Native Client 10.0 under both 32-bit and 64-bit architectures.
The command removes the properties aaa1 and aaa2.
It also sets the property aaa3 to bbb3 and the property aaa4 to bbb4.

### Example 4: Assign a value for a 32-bit driver by using a name and store the result
```
PS C:\> $Driver = Set-OdbcDriver -Name "SQL Server Native Client 10.0" -Platform "32-bit" -SetPropertyValue "aaa=bbb" -PassThru
```

This command assigns the key aaa a value of bbb for the 32-bit driver named SQL Server Native Client 10.0, and then stores the driver object in the $Driver variable.

### Example 5: Change and remove properties for a driver by using the pipeline operator
```
PS C:\> Get-OdbcDriver "SQL Server Native Client 10.0" -Platform "All" | Set-OdbcDriver -RemovePropertyValue @("aaa1", "aaa2") -SetPropertyValue @("aaa3=bbb3", "aaa4=bbb4")
```

This command operates on any driver named SQL Server Native Client 10.0 under both 32-bit and 64-bit architectures.
This command removes the properties aaa1 and aaa2.
It also sets the property aaa3 to bbb3 and the property aaa4 to bbb4.

### Example 6: Change and remove properties for a driver by using a variable
```
PS C:\> $DriverArray = Get-OdbcDriver "SQL Server Native Client 10.0" -Platform "All"
PS C:\> Set-OdbcDriver -InputObject $DriverArray -RemovePropertyValue @("aaa1", "aaa2") -SetPropertyValue @("aaa3=bbb3", "aaa4=bbb4")
```

The first command uses the Get-OdbcDriver cmdlet to get any driver named SQL Server Native Client 10.0 under both 32-bit and 64-bit architectures, and then stores them in the $DriverArray variable.

The second command removes the properties aaa1 and aaa2.
It also sets the property aaa3 to bbb3 and the property aaa4 to bbb4.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject
Aliases: Driver

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a driver.
You can use wildcard characters to specify more than one driver.
This cmdlet modifies one or more ODBC drivers that this parameter specifies.

```yaml
Type: String
Parameter Sets: Name
Aliases: DriverName

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
This cmdlet modifies an ODBC driver that belongs to the architecture that this parameter specifies.
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
This cmdlet removes the property values that this parameter specifies from the ODBC driver.
Specify an array of keys to be removed.

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
This cmdlet modifies or adds the values that this parameter specifies on an ODBC driver.
Specify an array of strings in the form \<key\>=\<value\>.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDriver[]

## NOTES

## RELATED LINKS

[Get-OdbcDriver](./Get-OdbcDriver.md)


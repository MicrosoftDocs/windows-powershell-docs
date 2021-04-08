---
author: Kateyanne
external help file: WDAC_Cmdlets.xml
manager: dansimp
Module Name: Wdac
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wdac/set-odbcdriver?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-OdbcDriver

## SYNOPSIS
Configure driver's properties for one or more installed ODBC drivers.
This configures driver's properties for one or more installed ODBC drivers.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-OdbcDriver [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-PassThru]
 [-RemovePropertyValue <String>] [-SetPropertyValue <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-OdbcDriver [-Name] <String> [-AsJob] [-CimSession <CimSession>] [-PassThru] [-Platform <String>]
 [-RemovePropertyValue <String>] [-SetPropertyValue <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
Set-OdbcDriver configures the properties for one or more installed ODBC drivers.
You can specify the properties to add or modify with the parameter SetPropertyValue, and specify the properties to remove with the parameter RemovePropertyValue.

You should use the driver installation program to install and uninstall a driver.
You cannot install or uninstall a driver using PowerShell Cmdlets.

For more information about ODBC and drivers, see Microsoft Open Database Connectivity (ODBC)http://msdn.microsoft.com/en-us/library/ms710252.aspx and Drivershttp://msdn.microsoft.com/en-us/library/ms715383.aspx.

## EXAMPLES

### 1:
```
PS C:\> Set-OdbcDriver "SQL Server Native Client 10.0" -Platform 32-bit -SetPropertyValue "CPTimeout=60"
```

This command sets the key "CPTimeout" to the value 60 for the 32-bit driver named "SQL Server Native Client 10.0":

### 2:
```
PS C:\> Set-OdbcDriver "SQL Server*" -RemovePropertyValue "aaa"
```

This command removes the property named "aaa" for all drivers with name started with "SQL Server" under the native platform:

### 3:
```
PS C:\> Set-OdbcDriver -Name "SQL Server Native Client 10.0" -Platform All -RemovePropertyValue @("aaa1", "aaa2") -SetPropertyValue @("aaa3=bbb3", "aaa4=bbb4")
```

This command removes the properties aaa1 and aaa2 and set the property aaa3 to bbb3 and aaa4 to bbb4 for driver named "SQL Server Native Client 10.0" under both 32-bit and 64-bit architectures:

### 4:
```
PS C:\> $driver = Set-OdbcDriver -Name "SQL Server Native Client 10.0" -Platform 32-bit -SetPropertyValue "aaa=bbb" -PassThru
```

This command sets the key "aaa" to the value "bbb" for the 32-bit driver named "SQL Server Native Client 10.0" and stores the driver object into a PowerShell variable:

### 5:
```
PS C:\> Get-OdbcDriver "SQL Server Native Client 10.0" -Platform All
| Set-OdbcDriver -RemovePropertyValue @("aaa1", "aaa2") -SetPropertyValue @("aaa3=bbb3", "aaa4=bbb4")
```

This command removes the properties aaa1 and aaa2 and sets the property aaa3 to bbb3 and aaa4 to bbb4 for driver named "SQL Server Native Client 10.0" under both 32-bit and 64-bit architectures and uses the pipeline objects returned from the command Get-OdbcDriver:

### 6:
```
PS C:\> $driverArray = Get-OdbcDriver "SQL Server Native Client 10.0" -Platform All
Set-OdbcDriver -InputObject $driverArray -RemovePropertyValue @("aaa1", "aaa2") -SetPropertyValue @("aaa3=bbb3", "aaa4=bbb4")
```

This command removes the properties aaa1 and aaa2 and sets the property aaa3 to bbb3 and aaa4 to bbb4 for driver named "SQL Server Native Client 10.0" under both 32-bit and 64-bit architectures and uses the PowerShell variable $driverArray:

## PARAMETERS

### -InputObject
Modifies the ODBC driver represented by the specified ODBC driver objects.
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
Specifies one or more ODBC drivers by driver name.
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

### -Platform
The platform architecture of the ODBC driver.
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

### -SetPropertyValue
Specifies the property values of the ODBC driver to be modified or added.
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
Specifies the property values of the ODBC driver to be deleted.
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
Passes the object created by this cmdlet through the pipeline.
By default, this cmdlet does not pass any objects through the pipeline.

Returns an object representing the modified ODBC Driver.
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_OdbcDriver[]

## NOTES

## RELATED LINKS

[Get-OdbcDriver](./Get-OdbcDriver.md)




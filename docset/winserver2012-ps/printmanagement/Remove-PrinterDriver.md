---
external help file: PrintMgmt_Cmdlets.xml
Module Name: PrintManagement
online version: https://learn.microsoft.com/powershell/module/printmanagement/remove-printerdriver?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-PrinterDriver

## SYNOPSIS
Deletes printer driver from the specified computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-PrinterDriver [-Name] <String> [[-PrinterEnvironment] <String>] [-AsJob] [-CimSession <CimSession>]
 [-ComputerName <String>] [-PassThru] [-RemoveFromDriverStore] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-PrinterDriver [-AsJob] [-CimSession <CimSession>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-PrinterDriver** cmdlet deletes a printer driver from the specified computer. 
You can specify the printer driver to remove by using either a printer object retrieved by Get-Printer, or by specifying a printer name.

You can use wildcard characters with **Remove-PrinterDriver**.
You can use **Remove-PrinterDriver** in a Windows PowerShell remoting session.

You need administrator privileges to use **Remove-PrinterDriver**.

## EXAMPLES

### Example1: Remove the printer driver
```
PS C:\> Remove-PrinterDriver -Name "Microsoft XPS Document Writer v4"
```

This command removes the "Microsoft XPS Document Writer v4" driver.

### Example2: Remove the printer driver using object
```
PS C:\>$PrinterDriver = Get-Printer -Name "Microsoft XPS Document Writer v4"




PS C:\>Remove-PrinterDriver -InputObject $PrinterDriver
```

This set of commands retrieves a printer object into a variable ($PrinterDriver) using Get-Printer, and then passes the contents of the variable to **Remove-PrinterDriver**.

## PARAMETERS

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

### -ComputerName
Specifies the computer name from which to remove the printer driver.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the object which contains the printer driver to remove.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer driver to remove.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
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

### -PrinterEnvironment
Specifies the printer driver environment.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveFromDriverStore
Specifies whether or not to remove the printer driver from the driver store.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrinterDriver
This cmdlet accepts one printer driver object.

## OUTPUTS

### 
By default, this cmdlet produces no output.

## NOTES

## RELATED LINKS

[Get-PrinterDriver](./Get-PrinterDriver.md)

[Add-PrinterDriver](./Add-PrinterDriver.md)


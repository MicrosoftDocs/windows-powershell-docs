---
external help file: PrintMgmt_Cmdlets.xml
Module Name: PrintManagement
online version: https://docs.microsoft.com/powershell/module/printmanagement/remove-printer?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-Printer

## SYNOPSIS
Removes a printer from the specified computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-Printer [-Name] <String> [-AsJob] [-CimSession <CimSession>] [-ComputerName <String>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-Printer [-AsJob] [-CimSession <CimSession>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-Printer** cmdlet deletes a printer from the specified computer.
You can specify the printer to remove by using either a printer object retrieved by Get-Printer, or by specifying a printer name.

You can use wildcard characters with **Remove-Printer**.
You can use **Remove-Printer** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Remove-Printer**.

## EXAMPLES

### -------------------------- EXAMPLE Example 1: Remove Delete a specific printer from the computer -------------------------- 
Example : Remove a specific printer
```
PS C:\> Remove-Printer -Name "Microsoft XPS Document Writer"
```

This command removes the printer named "Microsoft XPS Document Writer" from the local computer.

### Example 2: Remove a specific printer using a printer object
```
PS C:\>$printer = Get-Printer -Name "Microsoft XPS Document Writer"



PS C:\>Remove-Printer -InputObject $printer
```

This set of commands retrieves a printer object into a variable ($Printer) using Get-Printer, and then removes the specified printer using **Remove-Printer**.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ComputerName
Specifies the name of the computer from which to remove the printer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: Local machine name
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject
Specifies the object which contains the printer to remove.

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
Specifies the name of the printer to remove.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_Printer
This cmdlet accepts one printer object.

## OUTPUTS

### 
By default, this cmdlet produces no output.

## NOTES

## RELATED LINKS

[Add-Printer](./Add-Printer.md)

[Rename-Printer](./Rename-Printer.md)

[Get-Printer](./Get-Printer.md)

[Set-Printer](./Set-Printer.md)


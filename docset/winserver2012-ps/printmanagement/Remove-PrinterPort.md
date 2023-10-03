---
external help file: PrintMgmt_Cmdlets.xml
Module Name: PrintManagement
online version: https://learn.microsoft.com/powershell/module/printmanagement/remove-printerport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-PrinterPort

## SYNOPSIS
Removes the specified printer port from the specified computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-PrinterPort [-Name] <String> [-AsJob] [-CimSession <CimSession>] [-ComputerName <String>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-PrinterPort [-AsJob] [-CimSession <CimSession>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-PrinterPort** cmdlet removes the specified printer port from the specified computer.

You can remove a printer port by specifying the port name, or you can use a printer object retrieved using Get-PrinterPort.

You can use wildcard characters with **Remove-PrinterPort**.
You can use **Remove-PrinterPort** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Remove-PrinterPort**.

## EXAMPLES

### -------------------------- Example 1:  -------------------------- RemoveDelete a specificspecified printer port on a computer
xample: Remove a specified printer port
```
PS C:\> Remove-PrinterPort -Name "LocalPort:"
```

This command removes the printer port named LocalPort: from the computer.

### Example 2: Remove a specified printer port using a printer port object
```
PS C:\>$printerPort = Get-PrinterPort -Name "LocalPort:"



PS C:\>Remove-PrinterPort -InputObject $printerPort
```

This set of commands retrieves a printer port object into a variable ($printerPort) using Get-PrinterPort, and then passes the variable to **Remove-PrinterPort**.

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
Specifies the name of the computer from which to remove the printer port.

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
Specifies the printer port object which contains the printer port to remove.

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
Specifies the name of the printer port to remove.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrinterPort
This cmdlet accepts a printer port object.

## OUTPUTS

### 
By default, this cmdlet produces no output objects.

## NOTES

## RELATED LINKS

[Get-PrinterPort](./Get-PrinterPort.md)

[Add-PrinterPort](./Add-PrinterPort.md)


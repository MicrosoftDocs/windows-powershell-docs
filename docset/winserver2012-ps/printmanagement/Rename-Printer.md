---
external help file: PrintMgmt_Cmdlets.xml
Module Name: PrintManagement
online version: https://docs.microsoft.com/powershell/module/printmanagement/rename-printer?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-Printer

## SYNOPSIS
Renames the specified printer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-Printer [-Name] <String> [-NewName] <String> [-AsJob] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-Printer [-InputObject] <CimInstance> [-NewName] <String> [-AsJob] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Rename-Printer** cmdlet renames the specified printer on a computer.
You can specify the printer to rename by using either a printer object retrieved by Get-Printer, or by specifying a printer name.

You cannot use wildcard characters with **Rename-Printer**.
You can use **Rename-Printer** in a Windows PowerShell remoting session.

You need administrator privileges to use **Rename-Printer**.

## EXAMPLES

### -------------------------- Example 1: Rename a printer -------------------------- 
xample: Rename a printer
```
PS C:\> Rename-Printer -Name "Microsoft XPS Document Writer" -NewName "MXDW"
```

This command renames the "Microsoft XPS Document Writer" printer name as "MXDW".

### Example 2: Rename a printer by using a printer object
```
PS C:\>$Printer = Get-Printer -Name "Microsoft XPS Document Writer"



PS C:\>Rename-Printer -InputObject $Printer -NewName "MXDW"
```

This set of commands retrieves a printer object into a variable ($Printer) using Get-Printer, and then passes the contents of the variable to **Rename-Printer**.

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

### -InputObject
Specifies the object which contains the printer to rename.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer to rename.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -NewName
Specifies the new name of the printer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
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
This cmdlet produces no output.

## NOTES

## RELATED LINKS

[Add-Printer](./Add-Printer.md)

[Remove-Printer](./Remove-Printer.md)

[Get-Printer](./Get-Printer.md)

[Set-Printer](./Set-Printer.md)


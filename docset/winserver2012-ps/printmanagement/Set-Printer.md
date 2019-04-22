---
external help file: PrintMgmt_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: FED049DD-C64A-4A46-8A4C-37DFF8458DD7
manager: dansimp
---

# Set-Printer

## SYNOPSIS
Updates the configuration of an existing printer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-Printer [-Name] <String> [-AsJob] [-CimSession <CimSession>] [-Comment <String>] [-ComputerName <String>]
 [-Datatype <String>] [-DriverName <String>] [-KeepPrintedJobs <Boolean>] [-Location <String>] [-PassThru]
 [-PermissionSDDL <String>] [-PortName <String>] [-PrintProcessor <String>] [-Priority <UInt32>]
 [-Published <Boolean>] [-RenderingMode <RenderingModeEnum>] [-SeparatorPageFile <String>] [-Shared <Boolean>]
 [-ShareName <String>] [-StartTime <UInt32>] [-ThrottleLimit <Int32>] [-UntilTime <UInt32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-Printer [-AsJob] [-CimSession <CimSession>] [-Comment <String>] [-Datatype <String>] [-DriverName <String>]
 [-KeepPrintedJobs <Boolean>] [-Location <String>] [-PassThru] [-PermissionSDDL <String>] [-PortName <String>]
 [-PrintProcessor <String>] [-Priority <UInt32>] [-Published <Boolean>] [-RenderingMode <RenderingModeEnum>]
 [-SeparatorPageFile <String>] [-Shared <Boolean>] [-ShareName <String>] [-StartTime <UInt32>]
 [-ThrottleLimit <Int32>] [-UntilTime <UInt32>] -InputObject <CimInstance> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-Printer** cmdlet updates the configuration of the specified printer.

Use the **KeepPrintedJobs** parameter to make a printer keep printed jobs.

You can specify the printer to update by using either a printer object retrieved by Get-Printer, or by specifying a printer name.

You can use wildcard characters with **Set-Printer**.
You can use **Set-Printer** in a Windows PowerShell remoting session.

You need administrator privileges to use **Set-Printer**.

## EXAMPLES

### -------------------------- Example 1: Set printer to keep printed jobs -------------------------- 
xample: Set printer to keep printed jobs
```
PS C:\> Set-Printer -Name "Microsoft XPS Document Writer" -KeepPrintedJobs $true
```

This command configures the "Microsoft XPS Document Writer" printer to keep printed jobs.

### Example 2: Set printer to keep printed jobs by using a printer object
```
PS C:\>$printer = Get-Printer -Name "Microsoft XPS Document Writer"




PS C:\>$printer.KeepPrintedJobs = $true




PS C:\>Set-Printer -InputObject $printer
```

This set of commands retrieves a printer object in to a variable ($printer) using Get-Printer, and passes the contents of the variable to **Set-Printer**.

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

### -Comment
Specifies the text to add to the Comment field for the specified printer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer on which the printer is installed.

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

### -Datatype
Specifies the data type the printer uses to record print jobs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriverName
Specifies the name of the printer driver for the printer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the object which contains the printer information to update.

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

### -KeepPrintedJobs
Specifies whether the printer jobs in the queue are kept.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the location of the printer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer to modify.

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

### -PermissionSDDL
Specifies the permissions for the printer as an SDDL string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PortName
Specifies the name of the port used or created for the printer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrintProcessor
Specifies the name of the print processor used by the printer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
Specifies the relative queue priority.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Published
Specifies whether or not the printer is published in the network directory service.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RenderingMode
Specifies the rendering mode for the printer.
You can specify one of the following three rendering modes: SSR, CSR, or BOPD

```yaml
Type: RenderingModeEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: CSR
Accept pipeline input: False
Accept wildcard characters: False
```

### -SeparatorPageFile
Specifies the path to and name of the separator page to be used by the printer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShareName
Specifies the name by which to share the printer on the network.
To change the share state of a printer, specify the **Shared** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Shared
Changes the share state of the printer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies the starting time of printer availability.

```yaml
Type: UInt32
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

### -UntilTime
Specifies the ending time of printer availability.

```yaml
Type: UInt32
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_Printer
This cmdlet returns a printer object.

## NOTES

## RELATED LINKS

[Add-Printer](./Add-Printer.md)

[Get-Printer](./Get-Printer.md)

[Remove-Printer](./Remove-Printer.md)

[Rename-Printer](./Rename-Printer.md)


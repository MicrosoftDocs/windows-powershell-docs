---
external help file: PrintMgmt_Cmdlets.xml
Module Name: PrintManagement
online version: https://docs.microsoft.com/powershell/module/printmanagement/set-printconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-PrintConfiguration

## SYNOPSIS
Sets the configuration information for the specified printer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-PrintConfiguration [-PrinterObject] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-Collate <Boolean>]
 [-Color <Boolean>] [-DuplexingMode <DuplexingModeEnum>] [-PaperSize <PaperSizeEnum>]
 [-PrintTicketXml <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-PrintConfiguration [-PrinterName] <String> [-AsJob] [-CimSession <CimSession>] [-Collate <Boolean>]
 [-Color <Boolean>] [-ComputerName <String>] [-DuplexingMode <DuplexingModeEnum>] [-PaperSize <PaperSizeEnum>]
 [-PrintTicketXml <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-PrintConfiguration [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-PrintConfiguration** cmdlet sets the printer configuration for the specified printer. 
Using the **Set-PrintConfiguration** cmdlet, you can manage the configuration of the following features:

● Collate

● Color

● Duplexing Mode

● N-Up

● Paper Size

The **Set-PrintConfiguration** cmdlet also accepts print configuration objects using Get-PrintConfiguration cmdlet.

You cannot use wildcard characters with **Set-PrintConfiguration**.
You can use **Set-PrintConfiguration** in a Windows PowerShell remoting session.

You need administrator privileges to use **Set-PrintConfiguration**.

## EXAMPLES

### -------------------------- Example 1: Set the default paper size -------------------------- xample:Set the default paper size
```
PS C:\> Set-PrintConfiguration -PrinterName "Microsoft XPS Document Writer" -PaperSize A4
```

This command sets the default paper size of the printer named "Microsoft XPS Document Writer" printer to A4.

### Example 2: Set the default paper size using print configuration object
```
PS C:\>$PrintConfiguration = Get-PrintConfiguration -PrinterName "Microsoft XPS Document Writer"




PS C:\>$PrintConfiguration.paperSize = A4




PS C:\>Set-PrintConfiguration -InputObject $PrintConfiguration
```

This set of commands retrieves a print configuration object into a variable ($PrintConfiguration) using Get-PrintConfiguration, sets the paper size in the printer configuration object to A4 and then passes the contents of the variable to **Set-PrintConfiguration**.

### Example 3: Set the default paper size of all printers
```
PS C:\>$printers = get-printer * 
foreach ($printer in $printers)
{ 
    Set-printconfiguration -printerName $printer.name -PaperSize A4
}
```

This command gets all the printers into a variable $printers and then loops through all the printers and displays the properties.

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
Accept wildcard characters: False
```

### -Collate
Specifies whether or not to collate the output of the printer by default.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Color
Specifies whether the printer should use either color or grayscale printing by default.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer on which the printer is located.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -DuplexingMode
Specifies the duplexing mode the printer uses by default.

```yaml
Type: DuplexingModeEnum
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the object which contains the printer configuration settings to set.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PaperSize
Specifies the paper size the printer uses by default.

```yaml
Type: PaperSizeEnum
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrintTicketXml
Specifies the print ticket XML defining the default print settings for this printer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrinterName
Specifies the printer on which to set the configuration information.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the object which contains the printer on which to change the configuration settings.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
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
This cmdlet produces no output objects.

## NOTES

## RELATED LINKS

[Get-PrintConfiguration](./Get-PrintConfiguration.md)




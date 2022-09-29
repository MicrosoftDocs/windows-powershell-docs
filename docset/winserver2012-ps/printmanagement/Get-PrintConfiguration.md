---
external help file: PrintMgmt_Cmdlets.xml
Module Name: PrintManagement
online version: https://learn.microsoft.com/powershell/module/printmanagement/get-printconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-PrintConfiguration

## SYNOPSIS
Gets the configuration information of a printer.

## SYNTAX

### PrinterObject
```
Get-PrintConfiguration [-PrinterObject] <CimInstance> [-AsJob] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>]
```

### PrinterName
```
Get-PrintConfiguration [-PrinterName] <String> [-AsJob] [-CimSession <CimSession>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-PrintConfiguration** cmdlet gets the configuration information of the specified printer. 
Using **Get-PrintConfiguration** cmdlet, you can manage the configuration of the following features: 

- Collate
- Color
- Duplexing Mode
- N-Up
- Paper Size

You cannot use wildcard characters with **Get-PrintConfiguration**.
You can use **Get-PrintConfiguration** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Get-PrintConfiguration**.

## EXAMPLES

### Example 1: Get the printer configuration
```
PS C:\> Get-PrintConfiguration -PrinterName "Microsoft XPS Document Writer"
```

This command returns the printer configuration for the printer named "Microsoft XPS Document Writer".

### Example 2: Get the print configuration for all printers
```
PS C:\>$Printers = Get-Printer *
PS C:\>Foreach ($Printer in $Printers){Get-PrintConfiguration -PrinterName $Printer.name}
```

This command gets all the printers into a variable $printers and then loops through all the printers and displays the properties.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the name of the computer from which to retrieve the printer configuration information.

```yaml
Type: String
Parameter Sets: PrinterName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PrinterName
Specifies the name of the printer from which to retrieve the configuration information.

```yaml
Type: String
Parameter Sets: PrinterName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the object which contains the printer from which to retrieve configuration information.

```yaml
Type: CimInstance
Parameter Sets: PrinterObject
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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_Printer
This cmdlet accepts one printer object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_PrinterConfiguration
This cmdlet returns a printer configuration object.

## NOTES

## RELATED LINKS

[Set-PrintConfiguration](./Set-PrintConfiguration.md)

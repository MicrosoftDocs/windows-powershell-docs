---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_PrinterDriver_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 09/20/2021
online version: https://learn.microsoft.com/powershell/module/printmanagement/get-printerdriver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PrinterDriver
---

# Get-PrinterDriver

## SYNOPSIS
Retrieves the list of printer drivers installed on the specified computer.

## SYNTAX

```
Get-PrinterDriver [[-Name] <String[]>] [-PrinterEnvironment <String[]>] [-ComputerName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PrinterDriver** cmdlet retrieves the list of printer drivers installed on the specified computer.
The **Get-PrinterDriver** cmdlet returns a printer driver object that you can store in a variable to use with other cmdlets.
You can specify the *ComputerName* parameter to list the printer drivers installed on another computer.

You can use wildcard characters with **Get-PrinterDriver**.
You can use **Get-PrinterDriver** in a Windows PowerShell remoting session.

You do not need administrator credentials to run **Get-PrinterDriver**.

## EXAMPLES

### Example 1: Get a list of printer drivers using wildcard characters
```
Get-PrinterDriver -Name *
```

This command returns a list of printer drivers installed on the local computer by using wildcard characters.

### Example 2: Get a list of printer drivers on a remote computer
```
Get-PrinterDriver -Name * -ComputerName "PrintServer"
```

This command retrieves a list of printer drivers from the computer named PrintServer.

### Example 3: Get detailed information about each driver
```
Get-PrinterDriver -Name "Microsoft XPS Document Writer" | Format-List
```

This command displays the detailed information for each printer driver.
**Get-PrinterDriver** displays a summarized view of each printer driver queried.

### Example 4: Get a printer driver object
```
$PrinterDriver = Get-PrinterDriver -Name "Microsoft XPS Document Writer v4"
```

This command retrieves a printer driver object that you can use with other cmdlets.
The printer driver object is stored in the $PrinterDriver variable.

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

### -ComputerName
Specifies the name of the computer from which to retrieve the printer drivers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer driver to retrieve.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrinterEnvironment
Specifies the printer driver environment.

```yaml
Type: String[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrinterDriver
This cmdlet returns one or more printer driver objects.

## NOTES

## RELATED LINKS

[Add-PrinterDriver](./Add-PrinterDriver.md)

[Remove-PrinterDriver](./Remove-PrinterDriver.md)


---
external help file: MSFT_PrinterDriver_v1.0.cdxml-help.xml
Module Name: PrintManagement
online version: 
schema: 2.0.0
title: Get-PrinterDriver
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1712E3E2-BEAA-43A3-A1B3-B15F5FCCF768
ms.author: v-kaunu
ms.reviewer: brianlic
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
You can use the **ComputerName** parameter to list the printer drivers installed on another computer.

You can use wildcard characters with **Get-PrinterDriver**.
You can use **Get-PrinterDriver** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Get-PrinterDriver**.

## EXAMPLES

### Example 1: Get a list of printer drivers using wildcard characters
```
PS C:\>Get-PrinterDriver *
```

This command returns a list of printer drivers installed on the local computer using wildcard characters.

### Example 2: Get a list of printer drivers on a remote computer
```
PS C:\>Get-PrinterDriver * -ComputerName printServer
```

This command retrieves a list of printer drivers from the computer named printServer.

### Example 3: Get detailed information of each driver
```
PS C:\>Get-PrinterDriver -Name "Microsoft XPS Document Writer" | Format-List
```

**Get-PrinterDriver** displays a summarized view of each printer driver queried.
 

The following command displays the detailed information for each printer driver.

### Example 4: Get a printer driver object
```
PS C:\>$PrinterDriver = Get-PrinterDriver -Name "Microsoft XPS Document Writer v4"
```

This command retrieves a printer driver object that you can use with other cmdlets.
The printer driver object is stored in the $PrinterDriver variable.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrinterDriver
This cmdlet returns one or more printer driver objects.

## NOTES

## RELATED LINKS

[Add-PrinterDriver](./Add-PrinterDriver.md)

[Remove-PrinterDriver](./Remove-PrinterDriver.md)


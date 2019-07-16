---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_PrinterDriver_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-PrinterDriver
ms.reviewer:
ms.assetid: 1CBF356C-E2C6-4D56-AA74-99DF5A6B170A
---

# Remove-PrinterDriver

## SYNOPSIS
Deletes printer driver from the specified computer.

## SYNTAX

### Query (cdxml) (Default)
```
Remove-PrinterDriver [-Name] <String[]> [[-PrinterEnvironment] <String[]>] [-ComputerName <String>]
 [-RemoveFromDriverStore] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-PrinterDriver -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-PrinterDriver** cmdlet deletes a printer driver from the specified computer.
You can specify the printer driver to remove by using either a printer object retrieved by Get-Printer, or by specifying a printer name.

You can use wildcard characters with **Remove-PrinterDriver**.
You can use **Remove-PrinterDriver** in a Windows PowerShell remoting session.

You need administrator credentials to run **Remove-PrinterDriver**.

## EXAMPLES

### Example1: Remove the printer driver
```
PS C:\> Remove-PrinterDriver -Name "Microsoft XPS Document Writer v4"
```

This command removes the Microsoft XPS Document Writer v4 driver.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the computer name from which to remove the printer driver.

```yaml
Type: String
Parameter Sets: Query (cdxml)
Aliases: CN

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
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
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: 

Required: True
Position: 0
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
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveFromDriverStore
Specifies whether to remove the printer driver from the driver store.

```yaml
Type: SwitchParameter
Parameter Sets: Query (cdxml)
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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


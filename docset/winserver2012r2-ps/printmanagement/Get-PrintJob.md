---
external help file: MSFT_PrintJob_v1.0.cdxml-help.xml
Module Name: PrintManagement
online version: 
schema: 2.0.0
title: Get-PrintJob
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 88790E6D-ABEE-4B77-9FD0-E177ACFBE608
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-PrintJob

## SYNOPSIS
Retrieves a list of print jobs in the specified printer.

## SYNTAX

### name
```
Get-PrintJob [-ComputerName <String>] [-ID <UInt32>] [-PrinterName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### object
```
Get-PrintJob [-ID <UInt32>] [-PrinterObject] <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PrintJob** cmdlet retrieves the current print jobs in the specified printer. 
Use the **PrinterName** parameter to list the print jobs from the specified printer.

You cannot use wildcard characters with **Get-PrintJob**.
You can use **Get-PrintJob** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Get-PrintJob**.

## EXAMPLES

### Example 1: Get a list of print jobs
```
PS C:\> Get-PrintJob -PrinterName "PrinterName"
```

This command retrieves a list of print jobs on the printer named PrinterName.

### Example 2: Get a list of print jobs using a printer object
```
PS C:\> $printer = Get-Printer -Name "PrinterName:"
PS C:\> Get-PrintJob -InputObject $printer
```

This set of commands retrieves a printer object into a variable ($Printer) using Get-Printer, and then retrieves the list of print jobs on the printer specified by the printer object in the variable by using **Get-PrintJob**.

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
Specifies the name of the computer from which to retrieve the print job information.

```yaml
Type: String
Parameter Sets: name
Aliases: CN, computer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ID
Specifies the ID of the print job to retrieve. 
You can use wildcard characters.

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

### -PrinterName
Specifies the name of the printer from which to retrieve the print job information.

```yaml
Type: String
Parameter Sets: name
Aliases: PN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the printer object from which to retrieve the print job information.

```yaml
Type: CimInstance
Parameter Sets: object
Aliases: Printer

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_Printer
This cmdlet accepts one printer object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrintJob
This cmdlet returns one or more print job objects.

## NOTES

## RELATED LINKS

[Remove-PrintJob](./Remove-PrintJob.md)

[Restart-PrintJob](./Restart-PrintJob.md)

[Suspend-PrintJob](./Suspend-PrintJob.md)

[Resume-PrintJob](./Resume-PrintJob.md)


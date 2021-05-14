---
external help file: MSFT_PrintJob_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/printmanagement/suspend-printjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-PrintJob
---

# Suspend-PrintJob

## SYNOPSIS
Suspends a print job on the specified printer.

## SYNTAX

### jobObject
```
Suspend-PrintJob [-InputObject] <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### printerName
```
Suspend-PrintJob [-ComputerName <String>] [-ID] <UInt32> [-PrinterName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### printerObject
```
Suspend-PrintJob [-ID] <UInt32> [-PrinterObject] <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Suspend-PrintJob** cmdlet suspends a print job on the specified printer.
Use Resume-PrintJob to resume the suspended print job.

You can specify the print job to suspend by specifying the **PrinterName** and job **ID** parameters, specifying a printer object and the job **ID** parameter, or by specifying a print job object as an input.

You cannot use wildcard characters with **Suspend-PrintJob**.
You can use **Suspend-PrintJob** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Suspend-PrintJob**.

## EXAMPLES

### Example 1: Suspend a specific print job
```
PS C:\> Suspend-PrintJob -PrinterName "PrinterName" -ID 1
```

This command suspends the print job with an ID of 1 on the printer named PrinterName.

### Example 2: Suspend a print job using a printer object and print job ID
```
PS C:\>$printer = Get-Printer -Name "PrinterName:"


PS C:\>Suspend-PrintJob -PrinterObject $printer -ID 1
```

This set of commands retrieves a printer object into a variable ($printer) using Get-Printer, and then passes the contents of the variable to **Suspend-PrintJob** to suspend the print job with an ID of 1 on the printer contained in the printer object.

### Example 3: Suspend a print job using a print job object
```
PS C:\>$printJob = Get-PrintJob -PrinterName "Printer1" -ID 1


PS C:\>Suspend-PrintJob -InputObject $printJob
```

This set of commands retrieves a print job object with an ID of 1 into a variable ($printJob) using Get-PrintJob, and then passes the contents of the variable to **Suspend-PrintJob** to suspend the print job on the printer contained in the print job object.

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
Specifies the name of the computer on which to suspend a print job.

```yaml
Type: String
Parameter Sets: printerName
Aliases: CN, computer

Required: False
Position: Named
Default value: Local machine name
Accept pipeline input: True (ByPropertyName)
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

### -ID
Specifies the ID of the print job to suspend on the specified printer. 
You cannot use wildcard characters.

```yaml
Type: UInt32
Parameter Sets: printerName, printerObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the object which contains the print job to suspend on the specified printer.

```yaml
Type: CimInstance
Parameter Sets: jobObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrinterName
Specifies a printer name on which to suspend the print job.

```yaml
Type: String
Parameter Sets: printerName
Aliases: PN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the object which contains the printer on which to suspend the print job.

```yaml
Type: CimInstance
Parameter Sets: printerObject
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrintJob
This cmdlet accepts one print job object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-PrintJob](./Get-PrintJob.md)

[Remove-PrintJob](./Remove-PrintJob.md)

[Restart-PrintJob](./Restart-PrintJob.md)

[Resume-PrintJob](./Resume-PrintJob.md)


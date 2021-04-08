---
author: Kateyanne
external help file: PrintMgmt_Cmdlets.xml
manager: dansimp
Module Name: PrintManagement
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/printmanagement/resume-printjob?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Resume-PrintJob

## SYNOPSIS
Resumes a suspended print job.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Resume-PrintJob [-PrinterObject] <CimInstance> [-ID] <UInt32> [-AsJob] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Resume-PrintJob [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Resume-PrintJob [-ID] <UInt32> [-PrinterName] <String> [-AsJob] [-CimSession <CimSession>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Resume-PrintJob** cmdlet resumes a suspended print job on the specified printer. 
The **Resume-PrintJob** cmdlet has no effect if any print job is running.

You can specify the print job to resume by specifying the **PrinterName** and **ID** parameters, by specifying the printer object and job **ID** parameter, or by specifying the print job object as an input.

You cannot use wildcard characters with **Resume-PrintJob**.

## EXAMPLES

### -------------------------- Example 1: Resumes a suspendedelected print job -------------------------- xample: Resume a suspended print job
```
PS C:\> Resume-PrintJob - PrinterName "PrinterName" -ID 1
```

This command resumes the print job with an ID of 1,   which was suspended on the printer named PrinterName.

### Example 2: Resume a print job using a printer object and job ID
```
PS C:\>$printer = Get-Printer -PrinterName "PrinterName"



PS C:\>Resume-PrintJob -PrinterObject $printer -ID 1
```

This set of commands retrieves a printer object into a variable ($printer) using Get-Printer, and then passes the contents of the variable to **Resume-PrintJob** to resume the print job with an ID of 1 on the printer contained in the printer object.

### Example 3: Resume a print job using a job object
```
PS C:\>$printJob = Get-PrintJob - PrinterName "PrinterName" -ID 1



PS C:\>Resume-PrintJob -InputObject $printJob
```

This set of commands retrieves the print job with an ID of 1 into a variable ($printJob) using Get-PrintJob, and then passes the contents of the variable to **Resume-PrintJob** to resume the print job on a printer by using a print job object.

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
Specifies the name of the computer on which to resume the print job.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ID
Specifies the ID of the print job to resume on the specified printer.
You can use wildcard characters.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the object which contains the print job to resume on the specified printer.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrinterName
Specifies the name of the printer on which to resume the print job.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the object which contains the printer on which to resume the print job.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrintJob
This cmdlet accepts one print job object.

## OUTPUTS

### 
This cmdlet produces no output.

## NOTES

## RELATED LINKS

[Get-PrintJob](./Get-PrintJob.md)

[Remove-PrintJob](./Remove-PrintJob.md)

[Restart-PrintJob](./Restart-PrintJob.md)

[Suspend-PrintJob](./Suspend-PrintJob.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_Printer_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 09/20/2021
online version: https://learn.microsoft.com/powershell/module/printmanagement/set-printer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Printer
---

# Set-Printer

## SYNOPSIS
Updates the configuration of an existing printer.

## SYNTAX

### Name (Default)
```
Set-Printer [-Name] <String[]> [-ComputerName <String>] [-Comment <String>] [-Datatype <String>]
 [-DriverName <String>] [-UntilTime <UInt32>] [-KeepPrintedJobs <Boolean>] [-Location <String>]
 [-PermissionSDDL <String>] [-PortName <String>] [-PrintProcessor <String>] [-Priority <UInt32>]
 [-Published <Boolean>] [-RenderingMode <RenderingModeEnum>] [-SeparatorPageFile <String>] [-Shared <Boolean>]
 [-ShareName <String>] [-StartTime <UInt32>] [-DisableBranchOfficeLogging <Boolean>]
 [-BranchOfficeOfflineLogSizeMB <UInt32>] [-WorkflowPolicy <WorkflowPolicyEnum>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-Printer -InputObject <CimInstance[]> [-Comment <String>] [-Datatype <String>] [-DriverName <String>]
 [-UntilTime <UInt32>] [-KeepPrintedJobs <Boolean>] [-Location <String>] [-PermissionSDDL <String>]
 [-PortName <String>] [-PrintProcessor <String>] [-Priority <UInt32>] [-Published <Boolean>]
 [-RenderingMode <RenderingModeEnum>] [-SeparatorPageFile <String>] [-Shared <Boolean>] [-ShareName <String>]
 [-StartTime <UInt32>] [-DisableBranchOfficeLogging <Boolean>] [-BranchOfficeOfflineLogSizeMB <UInt32>]
 [-WorkflowPolicy <WorkflowPolicyEnum>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-Printer** cmdlet updates the configuration of the specified printer.

Use the *KeepPrintedJobs* parameter to make a printer keep printed jobs.

You can specify the printer to update by using either a printer object retrieved by the Get-Printer cmdlet, or by specifying a printer name.

You can use wildcard characters with **Set-Printer**.
You can use **Set-Printer** in a Windows PowerShell remoting session.

You need administrator credentials to run **Set-Printer**.

## EXAMPLES

### Example 1: Set printer to keep printed jobs
```
Set-Printer -Name "Microsoft XPS Document Writer" -KeepPrintedJobs $True
```

This command configures the Microsoft XPS Document Writer printer to keep printed jobs.

### Example 2: Set printer to keep printed jobs by using a printer object
```
$Printer = Get-Printer -Name "Microsoft XPS Document Writer"
$Printer.KeepPrintedJobs = $True
Set-Printer -InputObject $Printer
```

The first command gets the printer named Microsoft XPS Document Writer by using the Get-Printer cmdlet.
The command stores the result in the $Printer variable.

The second command assigns a value of $True to the **KeepPrintedJobs** property of the $Printer object.

The final command sets the value of revised value of $Printer.

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

### -BranchOfficeOfflineLogSizeMB
Specifies the maximum size, in megabytes, of the branch office remote offline log file for this printer.
You cannot specify this parameter for unshared queues or queues that do not have branch office enabled.

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
Parameter Sets: Name
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

### -DisableBranchOfficeLogging
Indicates whether branch office remote logging is disabled.
You cannot specify this parameter for unshared queues.

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

### -KeepPrintedJobs
Specifies whether the printer jobs in the queue are kept.

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
Type: String[]
Parameter Sets: Name
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
Specifies the name of the port that is used or created for the printer.

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
Specifies whether the printer is published in the network directory service.

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
The acceptable values for this parameter are:

- SSR
- CSR
- BranchOffice

```yaml
Type: RenderingModeEnum
Parameter Sets: (All)
Aliases:
Accepted values: SSR, CSR, BranchOffice

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SeparatorPageFile
Specifies the path of and name of the separator page to be used by the printer.

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
To change the share state of a printer, specify the *Shared* parameter.

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
Specifies whether the printer is shared.

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

### -WorkflowPolicy
Enables an administrator to associate a given printer with a specific Workflow application. This parameter does not allow the administrator to override the device-app association that was made using the device metadata service.

```yaml
Type: WorkflowPolicyEnum
Parameter Sets: (All)
Aliases:
Accepted values: Uninitialized, Disabled, Enabled

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_Printer
This cmdlet returns a printer object.

## NOTES

## RELATED LINKS

[Add-Printer](./Add-Printer.md)

[Get-Printer](./Get-Printer.md)

[Remove-Printer](./Remove-Printer.md)

[Rename-Printer](./Rename-Printer.md)


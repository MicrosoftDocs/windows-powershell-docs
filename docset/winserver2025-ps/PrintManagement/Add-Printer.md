---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_Printer_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 09/20/2021
online version: https://learn.microsoft.com/powershell/module/printmanagement/add-printer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Printer
---

# Add-Printer

## SYNOPSIS
Adds a printer to the specified computer.

## SYNTAX

### connection
```
Add-Printer [-ConnectionName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ap
```
Add-Printer [-Comment <String>] [-Datatype <String>] [-UntilTime <UInt32>] [-KeepPrintedJobs]
 [-Location <String>] [-SeparatorPageFile <String>] [-ComputerName <String>] [-Shared] [-ShareName <String>]
 [-StartTime <UInt32>] [-Name] <String> [-PermissionSDDL <String>] [-PrintProcessor <String>]
 [-Priority <UInt32>] [-Published] [-RenderingMode <RenderingModeEnum>] [-DisableBranchOfficeLogging]
 [-BranchOfficeOfflineLogSizeMB <UInt32>] [-WorkflowPolicy <WorkflowPolicyEnum>] [-DeviceURL <String>]
 [-DeviceUUID <String>] [-IppURL <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### port
```
Add-Printer [-Comment <String>] [-Datatype <String>] [-DriverName] <String> [-UntilTime <UInt32>]
 [-KeepPrintedJobs] [-Location <String>] [-SeparatorPageFile <String>] [-ComputerName <String>] [-Shared]
 [-ShareName <String>] [-StartTime <UInt32>] [-Name] <String> [-PermissionSDDL <String>]
 [-PrintProcessor <String>] [-Priority <UInt32>] [-Published] [-RenderingMode <RenderingModeEnum>]
 -PortName <String> [-DisableBranchOfficeLogging] [-BranchOfficeOfflineLogSizeMB <UInt32>]
 [-WorkflowPolicy <WorkflowPolicyEnum>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-Printer** cmdlet adds a printer to a specified computer.
You can add both local printers and connections to network-based printers.

You cannot use wildcard characters with **Add-Printer**.
You can use **Add-Printer** in a Windows PowerShell remoting session.

You may need administrative credentials to run **Add-Printer**.

## EXAMPLES

### Example 1: Add a printer to a local computer
```powershell
Add-Printer -Name "mxdw 2" -DriverName "Microsoft XPS Document Writer v4" -PortName "portprompt:"
```

This command adds a printer with name mxdw2 to the local computer.
The mxdw printer uses the Microsoft XPS Document Writer v4 driver and the `portprompt:` port.

The` portprompt:` port prompts for a file name to save the XPS document when printing to the XPS printer.

### Example 2: Add a new network printer connection
```powershell
Add-Printer -ConnectionName \\printServer\printerName
```

This command adds a printer by specifying the name of a print server and a shared printer on that server.

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
Parameter Sets: ap, port
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
Parameter Sets: ap, port
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer to which to add the printer.

```yaml
Type: String
Parameter Sets: ap, port
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

### -ConnectionName
Specifies the name of a shared printer to which to connect.
This parameter is required.

```yaml
Type: String
Parameter Sets: connection
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datatype
Specifies the data type the printer uses to record print jobs.

```yaml
Type: String
Parameter Sets: ap, port
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceURL
Specifies a URL for the directed discovery of a Web Services on Devices (WSD) printer to add to the specified computer.s

```yaml
Type: String
Parameter Sets: ap
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceUUID
Specifies the multicast UUID for device detection for the WSD port.

```yaml
Type: String
Parameter Sets: ap
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableBranchOfficeLogging
Indicates that branch office remote logging is disabled.
You cannot specify this parameter for unshared queues.

```yaml
Type: SwitchParameter
Parameter Sets: ap, port
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
Parameter Sets: port
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IppURL
Specifies a URL or hostname or IP address for the directed discovery of an IPP (Internet Printing Protocol) printer to add to the specified computer.

```yaml
Type: String
Parameter Sets: ap
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeepPrintedJobs
Specifies whether the print jobs in the queue are kept.

```yaml
Type: SwitchParameter
Parameter Sets: ap, port
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
Parameter Sets: ap, port
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer to add.

```yaml
Type: String
Parameter Sets: ap, port
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PermissionSDDL
Specifies the permissions for the printer as a Security Descriptor Definition Language (SDDL) string.

```yaml
Type: String
Parameter Sets: ap, port
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
Parameter Sets: port
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrintProcessor
Specifies the name of the print processor used by the printer.

```yaml
Type: String
Parameter Sets: ap, port
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
Parameter Sets: ap, port
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
Type: SwitchParameter
Parameter Sets: ap, port
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RenderingMode
Specifies the rendering mode for the printer.
You can specify one of the following rendering modes:

- SSR, Service Side Rendering
- CSR.
Client Side Rendering
- BranchOffice.
Branch Office

```yaml
Type: RenderingModeEnum
Parameter Sets: ap, port
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
Parameter Sets: ap, port
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Shared
Indicates whether to share the printer on the network.
You can determine the name by which the printer is shared by specifying **ShareName**.
If **ShareName** is not specified, the name of the printer is used as the share name.

```yaml
Type: SwitchParameter
Parameter Sets: ap, port
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShareName
Specifies the name by which to share the printer on the network.
To share a printer, specify the **Shared** parameter.

```yaml
Type: String
Parameter Sets: ap, port
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
Parameter Sets: ap, port
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
Parameter Sets: ap, port
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
Parameter Sets: ap, port
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

### System.String

## OUTPUTS

### System.Object
## NOTES

- The WhatIf switch doesn't work if the **ConnectionName** parameter set is used.

## RELATED LINKS

[Get-Printer](./Get-Printer.md)

[Set-Printer](./Set-Printer.md)

[Remove-Printer](./Remove-Printer.md)

[Rename-Printer](./Rename-Printer.md)


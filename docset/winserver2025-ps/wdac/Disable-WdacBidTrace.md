---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdacBidTraceTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/disable-wdacbidtrace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WdacBidTrace
---

# Disable-WdacBidTrace

## SYNOPSIS
Disables BidTrace for Windows DAC.

## SYNTAX

### InputObject (Default)
```
Disable-WdacBidTrace [-PassThru] [-InputObject] <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Path
```
Disable-WdacBidTrace [-PassThru] [-Platform <String>] [-Path] <String> [-ProcessId <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Folder
```
Disable-WdacBidTrace [-PassThru] [-Platform <String>] -Folder <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AllApp
```
Disable-WdacBidTrace [-PassThru] [-IncludeAllApplications] [-Platform <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WdacBidTrace** cmdlet disables Built-in Diagnostics Tracing (BidTrace) for troubleshooting Windows Data Access Components (Windows DAC).

For more information about data access tracing, see [Data Access Tracing (Windows 8)](https://msdn.microsoft.com/en-us/library/hh829624aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Disable BidTrace for a 32-bit application
```
PS C:\> Disable-WdacBidTrace -Path "C:\temp\abc.exe" -Platform "32-bit"
```

This command disables the BidTrace for the application C:\temp\abc.exe on the 32-bit platform.

### Example 2: Disable BidTrace for a 32-bit application by using a Process ID
```
PS C:\> Disable-WdacBidTrace -Path "C:\temp\abc.exe" -ProcessId 1234 -Platform "32-bit"
```

This command disables the BidTrace for the application C:\temp\abc.exe on the 32-bit platform, and disables BidTrace for the particular instance of abc.exe that has the Process ID 1234.

### Example 3: Disable BidTrace for all native applications in a folder
```
PS C:\> Disable-WdacBidTrace -Folder "C:\temp"
```

This command disables the BidTrace for all applications in C:\temp on the native platform.

### Example 4: Disable BidTrace for all 64-bit applications
```
PS C:\> Disable-WdacBidTrace -IncludeAllApplications -Platform "64-bit"
```

This command disables the BidTrace for all 64-bit applications.

### Example 5: Enable and disable BidTrace for a 64-bit application
```
PS C:\> $BidSetting = Enable-WdacBidTrace -Path "C:\temp\abc.exe" -Platform "64-bit" -PassThru
PS C:\> Disable-WdacBidTrace -InputObject $BidSetting
```

The first command enables the BidTrace for the 64-bit application C:\temp\abc.exe, and then stores the result in the $BidSetting variable.
After you run the first command, you can use abc.exe.

The second command disables BidTrace for the application stored in $BidSetting.

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

### -Folder
Specifies a folder.
This cmdlet disables BidTrace for applications under the folder that this parameter specifies.

```yaml
Type: String
Parameter Sets: Folder
Aliases: ApplicationFolder

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeAllApplications
Indicates that this cmdlet applies to all applications.
If you specify this parameter, the cmdlet disables BidTrace for all applications.

```yaml
Type: SwitchParameter
Parameter Sets: AllApp
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject
Aliases: BidTrace

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Path
Specifies the full path for an application.
This cmdlet disables BidTrace for the application that this parameter specifies.

```yaml
Type: String
Parameter Sets: Path
Aliases: ApplicationPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Platform
Specifies the platform architecture.
This cmdlet disables BidTrace for the Windows DAC BidTrace settings that belong to the architecture that this parameter specifies.
The acceptable values for this parameter are:

- 32-bit
- 64-bit
- All

The default value is 32-bit on a 32-bit process.
The default value is 64-bit on a 64-bit process.
If you run this cmdlet in a remote CIM session, this parameter refers to the platform architecture on the remote computer.

```yaml
Type: String
Parameter Sets: Path, Folder, AllApp
Aliases:
Accepted values: 32-bit, 64-bit, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProcessId
Specifies a process ID.
This cmdlet disables BidTrace for the process that has the ID that this parameter specifies.

```yaml
Type: UInt32
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdacBidTrace[]

## NOTES

## RELATED LINKS

[Enable-WdacBidTrace](./Enable-WdacBidTrace.md)

[Get-WdacBidTrace](./Get-WdacBidTrace.md)


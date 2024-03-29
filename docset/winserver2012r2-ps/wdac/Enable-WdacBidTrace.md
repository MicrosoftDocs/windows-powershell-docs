---
external help file: MSFT_WdacBidTraceTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/wdac/enable-wdacbidtrace?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WdacBidTrace
---

# Enable-WdacBidTrace

## SYNOPSIS
Enables BidTrace for troubleshooting Windows DAC.

## SYNTAX

### InputObject (Default)
```
Enable-WdacBidTrace [-PassThru] [-InputObject] <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Path
```
Enable-WdacBidTrace [-PassThru] [-Platform <String>] [-Path] <String> [-ProcessId <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Folder
```
Enable-WdacBidTrace [-PassThru] [-Platform <String>] -Folder <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AllApp
```
Enable-WdacBidTrace [-PassThru] [-IncludeAllApplications] [-Platform <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WdacBidTrace** cmdlet enables Built-in Diagnostics Tracing (BidTrace) for troubleshooting Windows Data Access Components (Windows DAC).

For more information about data access tracing, see [Data Access Tracing (Windows 8)](https://msdn.microsoft.com/en-us/library/hh829624(VS.85).aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Enable BidTrace for an application on a platform
```
PS C:\> Enable-WdacBidTrace -Path "C:\temp\abc.exe" -Platform "32-bit"
```

This command enables the BidTrace for the application C:\temp\abc.exe on the 32-bit platform.

### Example 2: Enable BidTrace for application by using a Process ID
```
PS C:\> Enable-WdacBidTrace -Path "C:\temp\abc.exe" -ProcessId 1234 -Platform "32-bit"
```

This command enables the BidTrace for the application C:\temp\abc.exe on the 32-bit platform for a particular instance of abc.exe.
The enabled application has the Process ID  1234.

### Example 3: Enable BidTrace for applications in a specified folder on the native platform
```
PS C:\> Enable-WdacBidTrace -Folder "C:\temp"
```

This command enables a BidTrace for all applications located in C:\temp on the native platform.

### Example 4: Enable BidTrace for 64-bit applications
```
PS C:\> Enable-WdacBidTrace -IncludeAllApplications -Platform "64-bit"
```

This command enables the BidTrace for all 64-bit applications.

### Example 5: Enable and disable BidTrace for an application
```
PS C:\> $bidSetting = Enable-WdacBidTrace -Path "C:\temp\abc.exe" -Platform "64-bit" -PassThru
PS C:\> Disable-WdacBidTrace -InputObject $bidSetting
```

The first command enables the BidTrace for the 64-bit application C:\temp\abc.exe, and then stores the result in the **$bidSetting** variable.
After you run the first command, you can use abc.exe.
The second command disables BidTrace for the application stored in **$bidSetting**.

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
This cmdlet enables BidTrace for all applications under the folder that this cmdlet specifies.

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
If you specify this parameter, the cmdlet enables BidTrace for all applications.

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
Specifies an array of input objects.
This cmdlet enables the BidTrace that the BidTrace setting objects that this parameter specifies represent.
Specify a variable that contains the objects, or type a command or expression that gets the objects.

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
Specifies the full path of an application.
This cmdlet enables BidTrace for the application that this parameter specifies.

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
This cmdlet enables BidTrace for the WDAC BidTrace settings that belong to the architecture that this parameter specifies.
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
This cmdlet enables BidTrace for the process that has the ID that this parameter specifies.

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
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdacBidTrace[]

## NOTES

## RELATED LINKS

[Disable-WdacBidTrace](./Disable-WdacBidTrace.md)

[Get-WdacBidTrace](./Get-WdacBidTrace.md)



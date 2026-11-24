---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdacBidTraceTask_v1.0.cdxml-help.xml
Module Name: Wdac
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/wdac/get-wdacbidtrace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WdacBidTrace
---

# Get-WdacBidTrace

## SYNOPSIS
Gets BidTrace settings.

## SYNTAX

### Path (Default)
```
Get-WdacBidTrace [-Platform <String>] [[-Path] <String>] [-ProcessId <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Folder
```
Get-WdacBidTrace [-Platform <String>] -Folder <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### AllApp
```
Get-WdacBidTrace [-Platform <String>] [-IncludeAllApplications] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WdacBidTrace** cmdlet gets a list of Built-in Diagnostics Tracing (BidTrace) settings for different applications.

For more information about data access tracing, see [Data Access Tracing (Windows 8)](https://msdn.microsoft.com/en-us/library/hh829624aspx) on the Microsoft Developer Network.

## EXAMPLES

### Example 1: Get all BidTrace settings
```
C:\PS>Get-WdacBidTrace
```

This command gets all BidTrace settings for both 32-bit and 64-bit platforms.

### Example 2: Get the BidTrace setting for an application on a platform
```
C:\PS>Get-WdacBidTrace -Path "C:\temp\abc.exe" -Platform "32-bit"
```

This command gets the BidTrace setting for the application C:\temp\abc.exe and the specific settings for all its process instances on the 32-bit platform.

### Example 3: Get the BidTrace setting for an application by using a Process ID
```
C:\PS>Get-WdacBidTrace -Path "C:\temp\abc.exe" -ProcessId 1234 -Platform "64-bit"
```

This command gets the BidTrace setting for the application C:\temp\abc.exe that has the Process ID 1234 on the 64-bit platform.

### Example 4: Get the BidTrace setting for an application by using a wildcard character
```
C:\PS>Get-WdacBidTrace -Path "C:\*\abc.exe" -Platform "64-bit"
```

This command gets the BidTrace setting for the specified application on the 64-bit platform.
The *Path* parameter uses a wildcard character.

### Example 5: Get the BidTrace setting for application in a specified folder
```
C:\PS>Get-WdacBidTrace -Folder "C:\temp" -Platform "32-bit"
```

This command gets the BidTrace setting for the application located inside C:\temp on the 32-bit platform.

### Example 6: Get the BidTrace setting for application in a folder that includes a wildcard character
```
C:\PS>Get-WdacBidTrace -Folder "C:\t*mp" -Platform "32-bit"
```

This command gets the BidTrace setting for the application in the specified location on the 32-bit platform.
The *Path* parameter uses a wildcard character.

### Example 7: Get the BidTrace settings for all 32-bit applications
```
C:\PS>Get-WdacBidTrace -IncludeAllApplications -Platform "32-bit"
```

This command gets the BidTrace settings for all 32-bit applications on the computer.

### Example 8: Get BidTrace settings for both platforms
```
C:\PS>$BidArray = Get-WdacBidTrace
```

This command gets all BidTrace settings for both 32-bit and 64-bit platforms, and then store the results in the $BidArray variable.

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

### -Folder
Specifies a folder.
This cmdlets gets Windows DAC BidTrace settings that are associated with the folder that this parameter specifies.
You can use wildcard characters.

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
If you specify this parameter, the cmdlet gets Windows DAC BidTrace settings for with all applications.

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

### -Path
Specifies the full path for an application.
This cmdlet gets Windows Data Access Components (Windows DAC) BidTrace settings for the application that this parameter specifies.
You can use wildcard characters.
If you do not specify this parameter, this cmdlet gets all Windows DAC BidTrace settings.

```yaml
Type: String
Parameter Sets: Path
Aliases: ApplicationPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Platform
Specifies the platform architecture.
This cmdlet gets Windows DAC BidTrace settings that belong to the architecture that this parameter specifies.
The acceptable values for this parameter are:

- 32-bit
- 64-bit
- All

The default value is 32-bit on a 32-bit process.
The default value is 64-bit on a 64-bit process.
If you run this cmdlet in a remote CIM session, this parameter refers to the platform architecture on the remote computer.

```yaml
Type: String
Parameter Sets: (All)
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
This cmdlet gets Windows DAC BidTrace settings for the process that has the ID that this parameter specifies.
If you do not specify this parameter, this cmdlet gets all Windows DAC BidTrace settings.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdacBidTrace[]

## NOTES

## RELATED LINKS

[Disable-WdacBidTrace](./Disable-WdacBidTrace.md)

[Enable-WdacBidTrace](./Enable-WdacBidTrace.md)


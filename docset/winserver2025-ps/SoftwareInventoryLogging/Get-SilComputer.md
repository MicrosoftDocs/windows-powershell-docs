---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftSil_Computer.cdxml-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 01/24/2017
online version: https://learn.microsoft.com/powershell/module/softwareinventorylogging/get-silcomputer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SilComputer
---

# Get-SilComputer

## SYNOPSIS
Displays the point in time values for specific server and operating system-related data.

## SYNTAX

```
Get-SilComputer [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SilComputer** cmdlet displays the point in time values for specific server and operating system-related data needed for most common inventory purposes.
The data is collected at the point in time when the cmdlet runs.

## EXAMPLES

### Example 1: Get Software Inventory Logging computer data
```
PS C:\> Get-SilComputer
ChassisSerialNumber       : 7ZQ7TJ1
CollectedDateTime         : 5/20/2013 3:18:42 PM
Model                     : Precision WorkStation T7400
Name                      : Server.Test.Contoso.com
NumberOfCores             : 4
NumberOfLogicalProcessors : 4
NumberOfProcessors        : 1
OSName                    : Microsoft Windows Server 2012 R2 Datacenter Preview
OSSku                     : 8
OSSuite                   : 400
OSSuiteMask               : 400
OSVersion                 : 6.3.9405
ProcessorFamily           : 179
ProcessorManufacturer     : GenuineIntel
ProcessorName             : Intel(R) Xeon(R) CPU           E5440  @ 2.83GHz
SystemManufacturer        : Dell Inc.
VmGuid                    :
```

This command displays the point in time values for all server and operating system-related data.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### Microsoft.Management.Infrastructure.CimInstance#root/InventoryLogging/MsftSil_Computer

## NOTES

## RELATED LINKS

[Get-SilComputerIdentity](./Get-SilComputerIdentity.md)

[Get-SilData](./Get-SilData.md)

[SIL_Cmdlets](./softwareinventorylogging.md)

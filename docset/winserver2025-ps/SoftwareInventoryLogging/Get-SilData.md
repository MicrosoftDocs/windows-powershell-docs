---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Msft_MiStreamTasks.cdxml-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 01/24/2017
online version: https://learn.microsoft.com/powershell/module/softwareinventorylogging/get-sildata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SilData
---

# Get-SilData

## SYNOPSIS
Displays a point in time collection of all Software Inventory Logging data.

## SYNTAX

```
Get-SilData [[-FileName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
**The Get-SilData** cmdlet displays a point in time collection from all Software Inventory Logging data sources.
If this cmdlet runs on a Hyper-V Windows Server host that is running at least Windows ServerÂ® 2012 R2, it will also display data from all guests that are also running at least Windows Server 2012 R2 running in virtual machines on that host.
Data is collected at the point in time when the cmdlet runs.

Windows Server running in guest virtual machines needs to have Software Inventory Logging started and inventory collection run at least once.
The default setting is stopped.

## EXAMPLES

### Example 1: Get Software Inventory Logging data
```
PS C:\> Get-SilData
Item   : __PARAMETERS
VmGuid : 15F8DF27-183C-46BE-A037-2D8797E75C1C
Item   : MsftSil_UalAccess (RoleGuid = "7fb09bd3-7fe6-435e-8348-7d8aefb6cea3")
VmGuid : 15F8DF27-183C-46BE-A037-2D8797E75C1C
Item   : MsftSil_Computer (Name = "Contoso-01.Server.Test.Contoso...)
VmGuid : 15F8DF27-183C-46BE-A037-2D8797E75C1C


PSComputerName :


ID          : KB999114
InstallDate : 5/15/2013


ChassisSerialNumber       : 7ZQ7TJ1
CollectedDateTime         : 5/20/2013 3:20:09 PM
Model                     : Precision WorkStation T7400
Name                      : Server01.Test.Contoso.com
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


ProductName             : Windows Server 2012 R2 Datacenter Preview
RoleGuid                : 10a9226f-50ee-49d8-a393-9a501d47ce04
RoleName                : File Server
SampleDate              : 5/18/2013
UniqueDeviceAccessCount : 32
UniqueUserAccessCount   : 55


ProductName             : Windows Server 2012 R2 Datacenter Preview
RoleGuid                : 7fb09bd3-7fe6-435e-8348-7d8aefb6cea3
RoleName                : Print and Document Services
SampleDate              : 5/18/2013
UniqueDeviceAccessCount : 2
UniqueUserAccessCount   : 6


ID             : {6B6533BD-1680-4368-908E-D50977561A86}
InstallDate    : 5/14/2013 12:00:00 AM
Name           : Microsoft Office Professional Plus 2010
Vendor         : Microsoft Corporation
Version        : 14.0.6029.1000
```

This command displays a point in time collection Software Inventory Logging data.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShellÂ® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -FileName
Specifies the name of a file.
This file is used by Software Inventory Logging to define the data sources.
By default, the Software Inventory Logging service looks for the file named silconfig.mof.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShellÂ® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### Microsoft.Management.Infrastructure.CimInstance#root/InventoryLogging/MsftSil_GuestData

### Microsoft.Management.Infrastructure.CimInstance#root/inventorylogging/__PARAMETERS

### Microsoft.Management.Infrastructure.CimInstance#root/inventorylogging/MsftSil_WindowsUpdate

### Microsoft.Management.Infrastructure.CimInstance#root/inventorylogging/MsftSil_Computer

### Microsoft.Management.Infrastructure.CimInstance#root/inventorylogging/MsftSil_UalAccess

### Microsoft.Management.Infrastructure.CimInstance#root/inventorylogging/MsftSil_Software

## NOTES

## RELATED LINKS

[Publish-SilData](./Publish-SilData.md)


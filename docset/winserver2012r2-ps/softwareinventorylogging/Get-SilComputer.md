---
external help file: MsftSil_Computer.cdxml-help.xml
Module Name: SoftwareInventoryLogging
online version: 
schema: 2.0.0
title: Get-SilComputer
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: FF6386DB-E933-4D0F-BF7F-65C3B11947C9
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-SilComputer

## SYNOPSIS
Displays the point in time values for specific server and operating system-related data.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see http://support.microsoft.com/kb/3000850.

## SYNTAX

```
Get-SilComputer [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SilComputer** cmdlet displays the point in time values for specific server and operating system-related data needed for most common inventory purposes.
The data is collected at the point in time when the cmdlet runs.

## EXAMPLES

### Example 1: Retrieve Software Inventory Logging computer data
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
```

This command displays the point in time values for all server and operating system-related data.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/InventoryLogging/MsftSil_Computer
This cmdlet returns an object that encapsulates miscellaneous properties from a computer.
That object includes the following properties: 

- **ChassisSerialNumber** (**System.String**)
- **CollectedDateTime** (**System.DateTime**)
- **Model** (**System.String**)
- **Name** (**System.String**)
- **NumberOfCores** (**System.UInt32**)
- **NumberOfLogicalProcessors** (**System.UInt32**)
- **NumberOfProcessors** (**System.UInt32**)
- **OSName** (**System.String**)
- **OSSku** (**System.UInt32**)
- **OSSuite** (**System.UInt32**)
- **OSSuiteMask** (**System.UInt32**)
- **OSVersion** (**System.String**)
- **ProcessorFamily** (**System.UInt32**)
- **ProcessorManufacturer** (**System.String**)
- **ProcessorName** (**System.String**)
- **SystemManufacturer** (**System.String**)

## NOTES

## RELATED LINKS


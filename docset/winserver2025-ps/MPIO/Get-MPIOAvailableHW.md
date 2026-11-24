---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MPIOAvailableHW.cdxml-help.xml
Module Name: MPIO
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/mpio/get-mpioavailablehw?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MPIOAvailableHW
---

# Get-MPIOAvailableHW

## SYNOPSIS
Lists devices available to the system that can be managed by the MSDSM for MPIO.

## SYNTAX

```
Get-MPIOAvailableHW [[-VendorId] <String[]>] [[-ProductId] <String[]>] [-BusType <BusType[]>]
 [-IsMultipathed <Boolean[]>] [-IsSPC3Supported <Boolean[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MPIOAvailableHW** cmdlet lists available hardware devices in the system that can be managed by the Microsoft Device Specific Module (MSDSM) for Multipath I/O (MPIO).

To add one of the devices to MSDSM supported hardware list, use the vendor identifier (ID) and product ID of the device that are outputs from this cmdlet as inputs for the **New-MSDSMSupportedHW** cmdlet.

## EXAMPLES

### Example 1: Get connected multipath-capable devices
```
PS C:\> Get-MPIOAvailableHW
```

This example returns a list of multipath-capable devices currently connected to the system.

### Example 2: Get connected multipath-capable devices for a bus type
```
PS C:\> Get-MPIOAvailableHW -BusType iSCSI
```

This example returns a list of multipath-capable devices currently connected to the system via iSCSI.

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

### -BusType
Specifies the bus type via which the device is connected to the system.
The acceptable values for this parameter are: iSCSI, SAS, and FibreChannel.

```yaml
Type: BusType[]
Parameter Sets: (All)
Aliases:
Accepted values: FibreChannel, iSCSI, SAS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -IsMultipathed
Specifies that the device is currently multipath enabled by Microsoft MPIO.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsSPC3Supported
Specifies whether the supported specification of the device is T10 SPC3 or a later version.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductId
Specifies the product ID of the device.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### -VendorId
Specifies the vendor ID of the device.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-MSDSMSupportedHW](./New-MSDSMSupportedHW.md)


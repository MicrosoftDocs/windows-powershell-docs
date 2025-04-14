---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PnpDevice.cdxml-help.xml
Module Name: PnpDevice
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pnpdevice/get-pnpdevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PnpDevice
---

# Get-PnpDevice

## SYNOPSIS
Returns information about PnP devices.

## SYNTAX

### ByInstanceId (Default)
```
Get-PnpDevice [[-InstanceId] <String[]>] [-Class <String[]>] [-PresentOnly] [-Status <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyName
```
Get-PnpDevice [-FriendlyName <String[]>] [-Class <String[]>] [-PresentOnly] [-Status <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPresence
```
Get-PnpDevice [-Class <String[]>] [-PresentOnly] [-Status <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByClass
```
Get-PnpDevice [-Class <String[]>] [-PresentOnly] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStatus
```
Get-PnpDevice [-Status <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-PnpDevice** cmdlet returns basic information about Plug and Play (PnP) devices.
The values returned are common to all devices.

## EXAMPLES

### Example 1: Get all PnP devices
```
PS C:\>Get-PnpDevice
Status     Class           FriendlyName                                                                     InstanceId
------     -----           ------------                                                                     ----------
OK         System          High precision event timer                                                       ACPI\PNP0103...
OK         AudioEndpoint   Remote Audio                                                                     SWD\MMDEVAPI...
OK         System          System board                                                                     ACPI\PNP0C01\1
OK         System          System board                                                                     ACPI\PNP0C01\A
OK         System          Motherboard resources                                                            ACPI\PNP0C02\4
Unknown    MEDIA           Microsoft Streaming Service Proxy                                                SW\{96E080C7...
OK         System          UMBus Enumerator                                                                 UMB\UMB\1&amp;84...
OK         Printer         \\prn-corp3\stug-2633-clr                                                        SWD\PRINTENU...
OK         PrintQueue      stug-2633-clr on prn-tsqa.contoso.com (redirected 1)             SWD\PRINTENU...
```

This command gets all devices known to PnP, whether they are present or not.

### Example 2: Get PnP devices by name
```
PS C:\>Get-PnpDevice -FriendlyName 'Generic USB Hub'
Status     Class           FriendlyName                                                                     InstanceId
------     -----           ------------                                                                     ----------
OK         USB             Generic USB Hub                                                                  USB\VID_0557...
OK         USB             Generic USB Hub                                                                  USB\VID_0409...
OK         USB             Generic USB Hub                                                                  USB\VID_8087...
OK         USB             Generic USB Hub                                                                  USB\VID_8087...
OK         USB             Generic USB Hub                                                                  USB\VID_0424...
OK         USB             Generic USB Hub                                                                  USB\VID_0424...
```

This command gets all the devices named Generic USB Hub.

### Example 3: Get PnP devices by ID
```
PS C:\>Get-PnpDevice -InstanceId 'USB\VID_8087&amp;PID_0024\5&amp;3541780&amp;0&amp;1'
Status     Class           FriendlyName                                                                     InstanceId
------     -----           ------------                                                                     ----------
OK         USB             Generic USB Hub                                                                  USB\VID_8087...
```

This command gets the device that has the specified instance ID.

### Example 4: Get present PnP devices in specified states
```
PS C:\>Get-PnpDevice -PresentOnly -Status ERROR,DEGRADED,UNKNOWN
Status     Class           FriendlyName                                                                     InstanceId
------     -----           ------------                                                                     ----------
Error                      PCI Serial Port                                                                  PCI\VEN_8086...
Error      Mouse           Microsoft PS/2 Mouse                                                             ACPI\PNP0F03...
Error                      PCI Simple Communications Controller                                             PCI\VEN_8086...
Error                      SAS Controller                                                                   PCI\VEN_8086...
Error      Keyboard        Standard PS/2 Keyboard                                                           ACPI\PNP0303...
```

This command gets all present devices that report a status of error, degraded, or unknown.

### Example 5: Get PnP devices of a class
```
PS C:\>Get-PnpDevice -Class 'Mouse'
Status     Class           FriendlyName                                                                     InstanceId
------     -----           ------------                                                                     ----------
OK         Mouse           HID-compliant mouse                                                              HID\VID_0557...
Error      Mouse           Microsoft PS/2 Mouse                                                             ACPI\PNP0F03...
OK         Mouse           Remote Desktop Mouse Device                                                      TERMINPUT_BU...
OK         Mouse           HID-compliant mouse                                                              HID\VID_045E...
```

This command gets all the devices that belong to the specified PnP class.

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

### -Class
Specifies an array of PnP classes for devices.
Some example values for this parameter are Monitor, DiskDrive, and Processor.

```yaml
Type: String[]
Parameter Sets: ByInstanceId, ByFriendlyName, ByPresence, ByClass
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies an array of friendly names for devices.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId
Specifies an array of unique instance ID of devices.

```yaml
Type: String[]
Parameter Sets: ByInstanceId
Aliases: DeviceId

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PresentOnly
Indicates that this cmdlet gets only those devices that are present when you issue the command.
Present devices are physically in the system or attached to it.

```yaml
Type: SwitchParameter
Parameter Sets: ByInstanceId, ByFriendlyName, ByPresence, ByClass
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Specifies an array of current status values of devices.
The acceptable values for this parameter are:

- OK
- ERROR
- UNKNOWN
- DEGRADED

```yaml
Type: String[]
Parameter Sets: ByInstanceId, ByFriendlyName, ByPresence, ByStatus
Aliases:
Accepted values: OK, ERROR, DEGRADED, UNKNOWN

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Cimv2/Win32_PnPEntity[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-PnpDevice](./Disable-PnpDevice.md)

[Enable-PnpDevice](./Enable-PnpDevice.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PnpDevice.cdxml-help.xml
Module Name: PnpDevice
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pnpdevice/enable-pnpdevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PnpDevice
---

# Enable-PnpDevice

## SYNOPSIS
Enables a PnP device.

## SYNTAX

### ByInstanceId (Default)
```
Enable-PnpDevice [-InstanceId] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Enable-PnpDevice -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-PnpDevice** cmdlet enables a Plug and Play (PnP) device.
You must use an Administrator account to enable a device.

## EXAMPLES

### Example 1: Enable a device
```
PS C:\>Enable-PnpDevice -InstanceId 'USB\VID_5986&;PID_0266&;MI_00\7&;1E5D3568&;0&;0000'
```

This command enables the device that has the specified instance ID.

### Example 2: Enable all disabled devices
```
PS C:\>Get-PnpDevice | Where-Object {$_.Problem -eq 22} | Enable-PnpDevice
```

This command gets all the PnP devices by using the **Get-PnpDevice** cmdlet, and then passes them to the **Where-Object** cmdlet by using the pipeline operator.
For more information, type `Get-Help Where-Object`.
That cmdlet drops the devices that do not have a **Problem** value of 22.
That problem code means that the device is disabled.
The current cmdlet enables those disabled devices.

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

### -InstanceId
Specifies an array of unique instance ID of devices.

```yaml
Type: String[]
Parameter Sets: ByInstanceId
Aliases: DeviceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns a WMI error code.
By default, this cmdlet does not return a value.

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
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Cimv2/Win32_PnPEntity[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Int32
This cmdlet generates a WMI error code.

## NOTES
* You must use an Administrator account for this cmdlet.

## RELATED LINKS

[Disable-PnpDevice](./Disable-PnpDevice.md)

[Get-PnpDevice](./Get-PnpDevice.md)


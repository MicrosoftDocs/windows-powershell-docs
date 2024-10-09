---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PnpDevice.cdxml-help.xml
Module Name: PnpDevice
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pnpdevice/get-pnpdeviceproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PnpDeviceProperty
---

# Get-PnpDeviceProperty

## SYNOPSIS
Gets detailed properties for a PnP device.

## SYNTAX

### ByInstanceId (Default)
```
Get-PnpDeviceProperty -InstanceId <String[]> [[-KeyName] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-PnpDeviceProperty -InputObject <CimInstance[]> [[-KeyName] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PnpDeviceProperty** cmdlet gets detailed properties for a Plug and Play (PnP) device.
You can specify a device by instance ID or by using the **Get-PnpDevice** cmdlet.

A device property is a key-value pair.
A property key takes the form {GUID} PID.
The property value is one of several types, such as **UTF-8**, **GUID**, **Uint32**, or **Boolean**.
The output object contains the typed data of a value, and the value type.
Many properties also have friendly names, in the form of DEVPKEY_XXX.

## EXAMPLES

### Example 1: Get properties for a device by using an ID
```
PS C:\>Get-PnpDeviceProperty -InstanceId 'SWD\PRINTENUM\{E82E5EFD-6616-4E4F-9A96-7D94554A8BF0}'
InstanceId KeyName                                   Type       Data
---------- -------                                   ----       ----
SWD\PRI... DEVPKEY_Device_DeviceDesc                 String     Local Print Queue
SWD\PRI... DEVPKEY_Device_HardwareIds                StringList {PRINTENUM\LocalPrintQueue}
SWD\PRI... DEVPKEY_Device_CompatibleIds              StringList {GenPrintQueue, SWD\GenericRaw, SWD\Generic}
SWD\PRI... DEVPKEY_Device_Class                      String     PrintQueue
SWD\PRI... DEVPKEY_Device_ClassGuid                  Guid       {1ED2BBF9-11F0-4084-B21F-AD83A8E6DCDC}
. . .
```

This command gets the PnP device properties for the device that has the specified ID.

### Example 2: Get properties for a device by using the pipeline
```
PS C:\>Get-PnpDevice -InstanceId 'SWD\PRINTENUM\{E82E5EFD-6616-4E4F-9A96-7D94554A8BF0}' | Get-PnpDeviceProperty
InstanceId KeyName                                   Type       Data
---------- -------                                   ----       ----
SWD\PRI... DEVPKEY_Device_DeviceDesc                 String     Local Print Queue
SWD\PRI... DEVPKEY_Device_HardwareIds                StringList {PRINTENUM\LocalPrintQueue}
SWD\PRI... DEVPKEY_Device_CompatibleIds              StringList {GenPrintQueue, SWD\GenericRaw, SWD\Generic}
SWD\PRI... DEVPKEY_Device_Class                      String     PrintQueue
SWD\PRI... DEVPKEY_Device_ClassGuid                  Guid       {1ED2BBF9-11F0-4084-B21F-AD83A8E6DCDC}
. . .
```

This command uses the **Get-PnpDevice** cmdlet to get the PnP device that has the specified ID.
The command passes that object to the current cmdlet by using the pipeline operator.
The current command gets the device properties for that device.

### Example 3: Get properties by using GUID-ID pairs
```
PS C:\>Get-PnpDeviceProperty -KeyName '{A45C254E-DF1C-4EFD-8020-67D146A850E0} 2', '{A45C254E-DF1C-4EFD-8020-67D146A850E0} 10', '{4340A6C5-93FA-4706-972C-7B648008A5A7} 3' -InstanceId 'SWD\PRINTENUM\{E82E5EFD-6616-4E4F-9A96-7D94554A8BF0}'
InstanceId KeyName                                   Type       Data
---------- -------                                   ----       ----
SWD\PRI... DEVPKEY_Device_DeviceDesc                 String     Local Print Queue
SWD\PRI... DEVPKEY_Device_ClassGuid                  Guid       {1ED2BBF9-11F0-4084-B21F-AD83A8E6DCDC}
SWD\PRI... DEVPKEY_Device_ProblemCode                UInt32     0
```

This command gets some of the properties of the PnP device that has the specified instance ID.
The command specifies three key names of properties to get.
The command specifies names as GUID-ID pairs.

### Example 4: Get properties by using DEVPKEY names
```
PS C:\>Get-PnpDeviceProperty -KeyName 'DEVPKEY_Device_DeviceDesc', 'DEVPKEY_Device_ClassGuid', 'DEVPKEY_Device_ProblemCode' -InstanceId 'SWD\PRINTENUM\{E82E5EFD-6616-4E4F-9A96-7D94554A8BF0}'
InstanceId KeyName                                   Type       Data
---------- -------                                   ----       ----
SWD\PRI... DEVPKEY_Device_DeviceDesc                 String     Local Print Queue
SWD\PRI... DEVPKEY_Device_ClassGuid                  Guid       {1ED2BBF9-11F0-4084-B21F-AD83A8E6DCDC}
SWD\PRI... DEVPKEY_Device_ProblemCode                UInt32     0
```

This command gets some of the properties of the PnP device that has the specified instance ID.
The command specifies three key names of properties to get.
The command specifies names as DEVPKEY short names.

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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyName
Specifies an array of key names.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Key

Required: False
Position: 0
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

### System.Int32, Win32_PnPDeviceProperty[]
This cmdlet generates an **Int32** WMI success or failure code, or an array of  **Win32_PnPDeviceProperty** objects that represent properties for a PnP device.
A **Win32_PnPDeviceProperty** object contains the following fields:

- **Device**.
The instance ID for the device with which this property is associated.
- **KeyName**.
The friendly name for the property.
If no friendly name exists, this matches the **Key** field.
- **Key**.
The unique \[GUID\]-ID pairing representing the property.
- **Data**.
The typed data associated with the key.
This value is defined in the classes which inherit from **Win32_PnPDeviceProperty**.
For example, a **Win32PnPDevicePropertySint32** object would be returned for an **Int32** property.
**Data** would be an **Int32** value in this case.
- **Type**.
The type of the binary data.
This is defined in the **PnpDeviceProperty.Type** enum.

## NOTES
* The objects returned by **Get-PnpDeviceProperty** are all of the **(WMI Object) Win32_PnPDeviceProperty** type. They are always of a WMI class inherited from Win32_PnPDeviceProperty. For example, a device may contain a **String** and signed **Int32** properties. The cmdlet returns a **Win32_PnPDeviceProperty** array, where the first object in the array is a **Win32_PnPDevicePropertyString** object and the second is a **Win32_PnPDevicePropertySint32** object. For each object type, there is a **Data** variable, of the given type, which contains the value of the property.

  The following is a full list of possible WMI classes and the type of the **Data** variable:

- **Win32_PnPDevicePropertyUint8**.
**Uint8**.
- **Win32_PnPDevicePropertyUint16**.
**Uint16**.
- **Win32_PnPDevicePropertyUint32**.
**Uint32**.
- **Win32_PnPDevicePropertyUint64**.
**Uint64**.
- **Win32_PnPDevicePropertySint8**.
**Sint8**.
- **Win32_PnPDevicePropertySint16**.
**Sint16**.
- **Win32_PnPDevicePropertySint32**.
**Sint32**.
- **Win32_PnPDevicePropertySint64**.
**Sint64**.
- **Win32_PnPDevicePropertyString**.
**String**.
- **Win32_PnPDevicePropertyBoolean**.
**Boolean**.
- **Win32_PnPDevicePropertyReal32**.
**Real32**.
- **Win32_PnPDevicePropertyReal64**.
**Real64**.
- **Win32_PnPDevicePropertyDateTime**.
**DateTime**.
- **Win32_PnPDevicePropertySecurityDescriptor**.
**Win32_SecurityDescriptor**.

- **Win32_PnPDevicePropertyBinary**.
**Uint8** array.
- **Win32_PnPDevicePropertyUint16Array**.
**Uint16** array.
- **Win32_PnPDevicePropertyUint32Array**.
**Uint32** array.
- **Win32_PnPDevicePropertyUint64Array**.
**Uint64** array.
- **Win32_PnPDevicePropertySint8Array**.
**Sint8** array.
- **Win32_PnPDevicePropertySint16Array**.
**Sint16** array.
- **Win32_PnPDevicePropertySint32Array**.
**Sint32** array.
- **Win32_PnPDevicePropertySint64Array**.
**Sint64** array.
- **Win32_PnPDevicePropertyStringArray**.
**String** array.
- **Win32_PnPDevicePropertyBooleanArray**.
**Boolean** array.
- **Win32_PnPDevicePropertyReal32Array**.
**Real32** array.
- **Win32_PnPDevicePropertyReal64Array**.
**Real64** array.
- **Win32_PnPDevicePropertyDateTimeArray**.
**DateTime** array.
- **Win32_PnPDevicePropertySecurityDescriptorArray**.
**Win32_SecurityDescriptor** array.

## RELATED LINKS

[Disable-PnpDevice](./Disable-PnpDevice.md)

[Enable-PnpDevice](./Enable-PnpDevice.md)

[Get-PnpDevice](./Get-PnpDevice.md)


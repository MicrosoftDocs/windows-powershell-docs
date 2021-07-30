---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/hcs/set-hcssystem?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HcsSystem
---

# Set-HcsSystem

## SYNOPSIS
Modifies settings for your StorSimple instance.

## SYNTAX

```
Set-HcsSystem [-Name <String>] [-Timezone <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HcsSystem** cmdlet modifies settings for your StorSimple instance.

## EXAMPLES

### Example 1: Modify a device name
```
PS C:\> Set-HcsSystem -Name "Contoso03"
InstanceId           : 7ad8891d-f04b-41c6-8634-0eb7e3945c0e
Name                 : Contoso03
Model                : 7700
SerialNumber         : SHX0923218G34GS
TimeZone             : (UTC-08:00) Pacific Time (US &amp; Canada)
CurrentController    : Controller1
ActiveController     : Controller1
Controller0Status    : Normal
Controller1Status    : Normal
SystemMode           : Normal
HcsSoftwareVersion   : 6.3.9600.16517
ApiVersion           : 9.0.0.0
VhdVersion           : 6.3.9600.16517
OSVersion            : 6.3.9600.0
Capacity             : 549755813888000
RemoteManagementMode : HttpsAndHttpEnabled
```

This command modifies the name of the device.

### Example 2: Set the time zone
```
PS C:\> Set-HcsSystem -Timezone "Eastern Standard Time"
InstanceId           : 7ad8891d-f04b-41c6-8634-0eb7e3945c0e 
Name                 : Contoso03
Model                : 7700
SerialNumber         : SHX0923218G34GS
TimeZone             : (UTC-05:00) Eastern Time (US &amp; Canada)
CurrentController    : Controller1
ActiveController     : Controller1
Controller0Status    : Normal
Controller1Status    : Normal
SystemMode           : Normal
HcsSoftwareVersion   : 6.3.9600.16517
ApiVersion           : 9.0.0.0
VhdVersion           : 6.3.9600.16517
OSVersion            : 6.3.9600.0
Capacity             : 549755813888000
RemoteManagementMode : HttpsAndHttpEnabled
```

This command sets the time zone of the device to Eastern Standard Time.

## PARAMETERS

### -Name
Specifies a name.
The cmdlet assigns the friendly name that you specify to the device.
This is not the DNS name or operating system name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timezone
Specifies the time zone for the device, such as Eastern Standard Time or Mountain Standard Time.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Platform.Support.SystemInfo
The SystemInfo object has the following properties:

- Guid InstanceId 
- String Name 
- String Model 
- String SerialNumber
- TimeZoneInfo TimeZone 
- ControllerId CurrentController 
- ControllerId ActiveController 
- ControllerStatus Controller0Status 
- ControllerStatus Controller1Status 
- SystemMode @SystemMode 
- Version HcsSoftwareVersion 
- Version ApiVersion 
- Version VhdVersion 
- Version OSVersion 
- UInt64 Capacity 
- RemoteManagementMode RemoteManagementMode

The ControllerId enumeration has the following values:

- Unknown = controller_id.CONTROLLER_ID_UNKNOWN
- None = controller_id.CONTROLLER_ID_NONE
- Controller0 = controller_id.CONTROLLER_ID_A
- Controller1 = controller_id.CONTROLLER_ID_B

The ControllerStatus enumeration has the following values:

- Normal 
- Recovery 
- Unreachable

The SystemMode enumeration has the following values:

- Normal
- Maintenance 
- Decommissioned

The RemoteManagementMode enumeration has the following values:

- HttpsAndHttpEnabled = 0
- HttpsEnabled = 1
- Disabled = 2

## NOTES

## RELATED LINKS



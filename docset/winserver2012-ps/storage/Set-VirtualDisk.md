---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/set-virtualdisk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VirtualDisk

## SYNOPSIS
Modifies the attributes of an existing virtual disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-NewFriendlyName <String>]
 [-OtherUsageDescription <String>] [-ThrottleLimit <Int32>] [-Usage <Usage>] -UniqueId <String>
```

### UNNAMED_PARAMETER_SET_2
```
Set-VirtualDisk [-Access <Access>] [-AsJob] [-CimSession <CimSession[]>] [-IsManualAttach <Boolean>]
 [-ThrottleLimit <Int32>] -Name <String>
```

### UNNAMED_PARAMETER_SET_3
```
Set-VirtualDisk [-Access <Access>] [-AsJob] [-CimSession <CimSession[]>] [-IsManualAttach <Boolean>]
 [-ThrottleLimit <Int32>] -UniqueId <String>
```

### UNNAMED_PARAMETER_SET_4
```
Set-VirtualDisk [-InputObject] <CimInstance[]> [-Access <Access>] [-AsJob] [-CimSession <CimSession[]>]
 [-IsManualAttach <Boolean>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_5
```
Set-VirtualDisk [-FriendlyName] <String> [-Access <Access>] [-AsJob] [-CimSession <CimSession[]>]
 [-IsManualAttach <Boolean>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_6
```
Set-VirtualDisk [-InputObject] <CimInstance[]> [-AsJob] [-CimSession <CimSession[]>]
 [-NewFriendlyName <String>] [-OtherUsageDescription <String>] [-ThrottleLimit <Int32>] [-Usage <Usage>]
```

### UNNAMED_PARAMETER_SET_7
```
Set-VirtualDisk [-FriendlyName] <String> [-AsJob] [-CimSession <CimSession[]>] [-NewFriendlyName <String>]
 [-OtherUsageDescription <String>] [-ThrottleLimit <Int32>] [-Usage <Usage>]
```

### UNNAMED_PARAMETER_SET_8
```
Set-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-NewFriendlyName <String>]
 [-OtherUsageDescription <String>] [-ThrottleLimit <Int32>] [-Usage <Usage>] -Name <String>
```

## DESCRIPTION
The **Set-VirtualDisk** cmdlet modifies the attributes of an existing virtual disk.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-VirtualDisk -FriendlyName VirtualDisk1 -NewFriendlyName "Storage For Contoso"
```

This example changes the friendly name of a virtual disk.

### EXAMPLE 2
```
PS C:\>Set-VirtualDisk -FriendlyName "Storage For Contoso" -IsManualAttach $False
```

This example attaches a virtual disk that is currently set to manual-attach.

## PARAMETERS

### -Access
Manages access permissions to the VirtualDisk object.

```yaml
Type: Access
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -FriendlyName
Specifies a friendly name for a disk.
The friendly name may be defined by a user and is not guaranteed to be unique.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_7
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsManualAttach
Specifies that the object is set as manual-attach.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of an object or setting.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_8
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewFriendlyName
Specifies the new name of the object.
The new name may be defined by a user.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherUsageDescription
Specifies the usage of this object.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8
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

### -UniqueId
Specifies an ID used to uniquely identify a Disk object in the system.
The ID persists through restarts.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Specifies the intended usage.

```yaml
Type: Usage
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Connect-VirtualDisk](./Connect-VirtualDisk.md)

[Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Show-VirtualDisk](./Show-VirtualDisk.md)


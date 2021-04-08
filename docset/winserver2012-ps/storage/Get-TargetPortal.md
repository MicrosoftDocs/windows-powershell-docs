---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/get-targetportal?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-TargetPortal

## SYNOPSIS
Returns a TargetPortal object.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-TargetPortal [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-UniqueId <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-TargetPortal [-AsJob] [-CimSession <CimSession[]>] [-IPv4Address <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-TargetPortal [-AsJob] [-CimSession <CimSession[]>] [-IPv6Address <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-TargetPortal [-AsJob] [-CimSession <CimSession[]>] [-StorageSubsystem <CimInstance>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-TargetPortal [-AsJob] [-CimSession <CimSession[]>] [-TargetPort <CimInstance>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-TargetPortal** cmdlet returns a TargetPortal object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-TargetPortal
```

This example gets all target portals.

### EXAMPLE 2
```
PS C:\>Get-TargetPortal -IPv4Address 192.168.0.1
```

This example gets the target portal with the IPv4 address of `192.168.0.1`.

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

### -IPv4Address
Represents a TCP/IP v4 address in `xxx.xxx.xxx.xxx` format.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Address
Represents a TCP/IP v6 address.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubsystem


```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetPort
Accepts a TargetPort object as input.
The Target Port CIM object is exposed by the Get-TargetPorthttp://technet.microsoft.com/library/4c139739-cda3-4379-b87b-60b1b4db8cd2 cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPort
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPortal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-TargetPort](./Get-TargetPort.md)


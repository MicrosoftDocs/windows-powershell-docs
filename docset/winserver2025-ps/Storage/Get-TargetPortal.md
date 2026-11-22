---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: TargetPortal.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-targetportal?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TargetPortal
---

# Get-TargetPortal

## SYNOPSIS
Returns a TargetPortal object.

## SYNTAX

### ByUniqueId (Default)
```
Get-TargetPortal [-UniqueId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByIPv4Address
```
Get-TargetPortal [-IPv4Address <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByIPv6Address
```
Get-TargetPortal [-IPv6Address <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByTargetPort
```
Get-TargetPortal [-TargetPort <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### BySubsystem
```
Get-TargetPortal [-StorageSubsystem <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
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

### -IPv4Address
Represents a TCP/IP v4 address in `xxx.xxx.xxx.xxx` format.

```yaml
Type: String[]
Parameter Sets: ByIPv4Address
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
Parameter Sets: ByIPv6Address
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubsystem
Specifies a storage subsystem, as a **CimInstance** object.
The cmdlet gets target portals exposed by the storage subsystem that you specify.
To obtain a storage subsystem object, use the Get-StorageSubSystem cmdlet.

```yaml
Type: CimInstance
Parameter Sets: BySubsystem
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetPort
Accepts a TargetPort object as input.
The Target Port CIM object is exposed by the [Get-TargetPort](https://technet.microsoft.com/library/4c139739-cda3-4379-b87b-60b1b4db8cd2) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByTargetPort
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
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPort
You can use the pipeline operator to pass a TargetPort object to the *TargetPort* parameter to get the TargetPortal object associated with the specified target port.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPortal
This cmdlet returns an object that represents the target portal.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-TargetPort](./Get-TargetPort.md)


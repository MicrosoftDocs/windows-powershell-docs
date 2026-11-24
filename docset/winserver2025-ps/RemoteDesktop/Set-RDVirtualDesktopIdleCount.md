---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdvirtualdesktopidlecount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDVirtualDesktopIdleCount
---

# Set-RDVirtualDesktopIdleCount

## SYNOPSIS
Sets the maximum number of idle virtual desktops on host servers.

## SYNTAX

### Default (Default)
```
Set-RDVirtualDesktopIdleCount [-IdleCount] <Int32> [[-HostServer] <String[]>] [-ConnectionBroker <String>]
 [-BatchSize <Int32>] [<CommonParameters>]
```

### Allocation
```
Set-RDVirtualDesktopIdleCount [-Allocation] <Hashtable> [-ConnectionBroker <String>] [-BatchSize <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDVirtualDesktopIdleCount** cmdlet sets the maximum number of active but idle virtual desktops on one or more host servers.
This cmdlet sets the total number of virtual desktops that can be idle in all pools.

An idle virtual desktop is a virtual machine that is in a running state and there is no user logged on to it.
Idle virtual desktops continue to run even if you configured the pool so that the server saves a virtual desktop that is not in use.

## EXAMPLES

### Example 1: Set the number of idle virtual desktops on host servers
```
PS C:\>Set-RDVirtualDesktopIdleCount -IdleCount 10 -HostServer @("rdvh-1.contoso.com","rdvh-2.contoso.com") -ConnectionBroker "rdcb.contoso.com"
```

This command sets the maximum number of active but idle virtual desktops on the host servers named rdvh-1.contoso.com and rdvh-2.contoso.com.

### Example 2: Allocate idle virtual desktops to host servers
```
PS C:\>Set-RDVirtualDesktopIdleCount -Allocation @{"RDS-WKS-A26.contoso.com"=2;" RDS-WKS-A27.contoso.com"=4} -ConnectionBroker "rdcb.contoso.com"
```

This command sets the number of idle virtual desktops for specific host servers.
The command allocates 2 idle virtual desktops for the host server named RDS-WKS-A26.contoso.com, and 4 idle virtual desktops for the host server named RDS-WKS-A27.contoso.com.

## PARAMETERS

### -Allocation
Specifies a collection of values (key/value pair) that allocate idle virtual desktops to Remote Desktop Virtualization (RD Virtualization Host) servers.

```yaml
Type: Hashtable
Parameter Sets: Allocation
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BatchSize
Specifies the batch size.

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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### -HostServer
Specifies an array of names of the servers that host the session.
For session collections the host server has the name of the Remote Desktop Session Host (RD Session Host) server.
For virtual desktop collections the host server has the name of the Remote Desktop Virtualization Host (RD Virtualization Host) server.

```yaml
Type: String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleCount
Specifies the number of idle virtual desktops.

```yaml
Type: Int32
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-RDVirtualDesktopIdleCount](./Get-RDVirtualDesktopIdleCount.md)

[Get-RDVirtualDesktop](./Get-RDVirtualDesktop.md)


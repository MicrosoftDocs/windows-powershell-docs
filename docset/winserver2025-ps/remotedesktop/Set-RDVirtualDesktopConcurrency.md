---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdvirtualdesktopconcurrency?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDVirtualDesktopConcurrency
---

# Set-RDVirtualDesktopConcurrency

## SYNOPSIS
Sets the number of virtual desktops that RDS can create in parallel.

## SYNTAX

### Default (Default)
```
Set-RDVirtualDesktopConcurrency [-ConcurrencyFactor] <Int32> [[-HostServer] <String[]>]
 [-ConnectionBroker <String>] [-BatchSize <Int32>] [<CommonParameters>]
```

### Allocation
```
Set-RDVirtualDesktopConcurrency [-Allocation] <Hashtable> [-ConnectionBroker <String>] [-BatchSize <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDVirtualDesktopConcurrency** cmdlet sets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel on Remote Desktop Virtualization Host (RD Virtualization Host) servers.

## EXAMPLES

### Example 1: Set the number of virtual desktops that RDS can create in parallel on all host servers
```
PS C:\> Set-RDVirtualDesktopConcurrency -ConnectionBroker "rdcb.contoso.com" -ConcurrencyFactor 4
```

This command sets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel to 4 on all the host servers associated with the RD Connection Broker server named rdcb.contoso.com.

### Example 2: Set the number of virtual desktops that RDS can create in parallel on host servers
```
PS C:\> Set-RDVirtualDesktopConcurrency -ConnectionBroker "rdcb.contoso.com" -ConcurrencyFactor 3 -HostServer @("rdvh-1.contoso.com","rdvh-2.contoso.com")
```

This command sets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel to 3 on the host servers named rdvh-1.contoso.com and rdvh-2.contoso.com.

## PARAMETERS

### -Allocation
Specifies a collection of values (key/value pair) that specify the concurrency factor for each RD Virtualization Host server.

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

### -ConcurrencyFactor
Specifies the number of virtual desktops that RDS can create in parallel.

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
Specifies the name of the server that hosts the session.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDVirtualDesktopConcurrency](./Get-RDVirtualDesktopConcurrency.md)


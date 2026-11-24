---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdvirtualdesktopconcurrency?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDVirtualDesktopConcurrency
---

# Get-RDVirtualDesktopConcurrency

## SYNOPSIS
Gets the number of virtual desktops that RDS can create in parallel.

## SYNTAX

```
Get-RDVirtualDesktopConcurrency [[-HostServer] <String[]>] [-ConnectionBroker <String>] [-BatchSize <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDVirtualDesktopConcurrency** cmdlet gets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel on one or more Remote Desktop Virtualization Host (RD Virtualization Host) servers.

## EXAMPLES

### Example 1: Get the number of virtual desktops that RDS can create in parallel on host servers
```
PS C:\> Get-RDVirtualDesktopConcurrency -ConnectionBroker "rdcb.contoso.com" -HostServer @("rdvh-1.contoso.com","rdvh-2.contoso.com")
```

This command gets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel on the host servers named rdvh-1.contoso.com and rdvh-2.contoso.com.

### Example 2: Get the number of virtual desktops that RDS can create in parallel on all host servers
```
PS C:\> Get-RDVirtualDesktopConcurrency -ConnectionBroker "rdcb.contoso.com"
```

This command gets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel on all the host servers associated with the RD Connection Broker server named rdcb.contoso.com.

## PARAMETERS

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
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-RDVirtualDesktopConcurrency](./Set-RDVirtualDesktopConcurrency.md)


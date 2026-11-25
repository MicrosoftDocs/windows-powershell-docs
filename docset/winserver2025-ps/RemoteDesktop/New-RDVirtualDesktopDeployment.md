---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/new-rdvirtualdesktopdeployment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-RDVirtualDesktopDeployment
---

# New-RDVirtualDesktopDeployment

## SYNOPSIS
Installs role services for Virtual Desktop Infrastructure.

## SYNTAX

```
New-RDVirtualDesktopDeployment [-ConnectionBroker] <String> [-VirtualizationHost] <String[]>
 [[-WebAccessServer] <String>] [-CreateVirtualSwitch] [<CommonParameters>]
```

## DESCRIPTION
The **New-RDVirtualDesktopDeployment** cmdlet installs the role services that Virtual Desktop Infrastructure (VDI) requires to create a virtual machine-based desktop deployment.
You can specify the **CreateVirtualSwitch** parameter to create a pooled virtual desktop collection in addition to installing the role services.

In Windows Server® 2012, the Microsoft Virtual Desktop Infrastructure (VDI) deployment is a scenario-based installation that allows you to install, configure, and manage your virtual desktops from a central location.

## EXAMPLES

### Example 1: Create a virtual desktop deployment
```
PS C:\> New-RDVirtualDesktopDeployment -ConnectionBroker "rdcb.contoso.com" -WebAccessServer "rdwa.contoso.com" -VirtualizationHost "rdsh.contoso.com" -CreateVirtualSwitch
```

This command installs the role services that Virtual Desktop Infrastructure (VDI) requires to create a virtual machine-based desktop deployment.
The command uses the **CreateVirtualSwitch** parameter to create a pooled virtual desktop collection.

### Example 2: Install role services for Virtual Desktop Infrastructure
```
PS C:\> New-RDVirtualDesktopDeployment -ConnectionBroker "rdcb.contoso.com" -WebAccessServer "rdwa.contoso.com" -VirtualizationHost @("rdsh-1.contoso.com","rdsh-2.contoso.com")
```

This command installs the role services that Virtual Desktop Infrastructure (VDI) requires to create a virtual machine-based desktop deployment.
The command installs the Remote Desktop Web Access (RD Web Access) role service on the server named rdwa.contoso.com, and installs the Virtualization Host (RD Virtualization Host) role service on the servers named rdsh-1.contoso.com and rdsh-2.contoso.com.
The command does not create a pooled virtual desktop collection.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateVirtualSwitch
Indicates that VDI creates a pooled virtual desktop collection that is based on a virtual hard disk of the virtual desktop template.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualizationHost
Specifies the fully qualified domain name (FQDN) of the server that you want to run the Virtualization Host (RD Virtualization Host) role service.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebAccessServer
Specifies the fully qualified domain name (FQDN) of the server that you want to run the Remote Desktop Web Access (RD Web Access) role service.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

[New-RDSessionDeployment](./New-RDSessionDeployment.md)


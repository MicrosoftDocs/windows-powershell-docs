---
author: Kateyanne
external help file: IpamServer_Cmdlets.xml
manager: dansimp
Module Name: IpamServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/ipamserver/set-ipamconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-IpamConfiguration

## SYNOPSIS
Sets the configuration for the computer running the IP Address Management (IPAM) server, including the TCP port number over which the computer running the IPAM Remote Server Administration Tools (RSAT) client connects with the computer running the IPAM server.

## SYNTAX

```
Set-IpamConfiguration [-Port] <UInt16> [-Force] [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-IpamConfiguration** cmdlet sets the IP Address Management (IPAM) server configuration, including the TCP port over which the computer running the IPAM Remote Server Administration Tools (RSAT) client connects and communicates with the computer running the IPAM server.
This cmdlet can be leveraged to specify an alternate firewall port number for remotely managing the computer running the IPAM server, in the event of a port conflict.
The default port number used by IPAM is `48885`.
The cmdlet configures appropriate custom IPAM server firewall rules for the specified new port, enables appropriate custom IPAM server firewall rules for the specified new port, and restarts the IPAM application pool to listen on the specified new port.
This cmdlet must be run from an elevated Windows PowerShell® prompt with administrator privileges on the computer running the IPAM server.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-IpamServerConfiguration -Port 45000 -PassThru -Force
Version : 1.3 
 
Port : 45000
```

This example changes the IPAM server management port to 45000 and suppresses the default confirmation text and returns the modified IPAM server configuration object.

## PARAMETERS

### -Force
Suppresses the default confirmation text.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Port
Specifies the TCP port number being configured for communication between computers running the IPAM RSAT client and IPAM server.
The required firewall rules are also set up for this port.
Although IPAM allows any port number from `1` through `65535` to be configured for communication between computers running the IPAM client and server; it is recommended, to avoid port conflicts with well-known ports, that a port from the unassigned port range `48620` through `49150` is selected.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamConfiguration
This object contains an IPAM configuration.

## NOTES

## RELATED LINKS

[Get-IpamConfiguration](./Get-IpamConfiguration.md)


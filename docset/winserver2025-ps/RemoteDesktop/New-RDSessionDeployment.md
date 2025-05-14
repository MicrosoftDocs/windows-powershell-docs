---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/new-rdsessiondeployment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-RDSessionDeployment
---

# New-RDSessionDeployment

## SYNOPSIS
Installs the required role services for session-based desktop deployment.

## SYNTAX

```
New-RDSessionDeployment [-ConnectionBroker] <String> [-SessionHost] <String[]> [[-WebAccessServer] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-RDSessionDeployment** cmdlet installs role services required for the Virtual Desktop Infrastructure (VDI) to create a Remote Desktop Services (RDS) session-based Remote Desktop deployment.
A session-based deployment allows users to connect to session collections that include published Windows Server 2012 RemoteApp programs and session-based desktops.

Specify the fully qualified domain names (FQDN) for servers to host a Remote Desktop Connection Broker (RD Connection Broker) role service, a Remote Desktop Web Access (RD Web Access) role service, and one or more instances of the Remote Desktop Session Host (RD Session Host) role service.

## EXAMPLES

### Example 1: Install role services for a session deployment
```
PS C:\> New-RDSessionDeployment -ConnectionBroker "RDCB.Contoso.com" -WebAccessServer "RDWA.Contoso.com" -SessionHost "RDSH01.Contoso.com"
```

This command installs Remote Desktop role services on specified servers.
The command installs an RD Connection Broker role service on the server named RDCB.Contoso.com.
The command installs an RD Web Access role service on the server named RDWA.Contoso.com.
The command installs the RD Session Host role service on the server named RDSH01.Contoso.com.

### Example 2: Install role services that include multiple RD Session Host servers
```
PS C:\> New-RDSessionDeployment -ConnectionBroker "RDCB.Contoso.com" -WebAccessServer "RDWA.Contoso.com" -SessionHost @("RDSH01.Contoso.com","RDSH02.Contoso.com")
```

This command installs Remote Desktop role services on specified servers.
The command installs an RD Connection Broker role service on the server named RDCB.Contoso.com.
The command installs an RD Web Access role service on the server named RDWA.Contoso.com.
The command installs the RD Session Host role service on two servers, named RDSH01.Contoso.com and RDSH02.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the FQDN of a server to host the RD Connection Broker role service.

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

### -SessionHost
Specifies an array of the FQDNs of servers to host the RD Session Host role service.

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
Specifies the FQDN of a server to host the RD Web Access role service.

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


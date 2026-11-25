---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdsessionhost?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDSessionHost
---

# Set-RDSessionHost

## SYNOPSIS
Configures one or more RD Session Host servers in a session collection.

## SYNTAX

```
Set-RDSessionHost [-SessionHost] <String[]> [-NewConnectionAllowed] <RDServerNewConnectionAllowed>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDSessionHost** cmdlet configures one or more Remote Desktop Session Host (RD Session Host) servers in a session collection by specifying whether each server can accept new connections.
RD Session Host is a Remote Desktop Services role service that lets users share Windows-based programs or the full Windows desktop.
Users can connect to a RD Session Host server to run programs, save files, and use network resources on that server.

## EXAMPLES

### Example 1: Set values for an RD  Session Host server
```
PS C:\> Set-RDSessionHost -SessionHost "rdsh.contoso.com" -NewConnectionAllowed Yes -ConnectionBroker "rdcb.contoso.com"
```

This command specifies values for an RD Session Host server named rdsh.contoso.com.
Users can make new server connections to a session collection on the RD Connection Broker server named rdcb.contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
If this parameter does not appear, the default value is the fully qualified domain name (FQDN) of the local host.

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

### -NewConnectionAllowed
Determines whether the RD Session Host servers specified by the **SessionHost** parameter can accept new connections.
The acceptable values for this parameter are: Yes, NotUntilReboot, or No.

```yaml
Type: RDServerNewConnectionAllowed
Parameter Sets: (All)
Aliases:
Accepted values: Yes, NotUntilReboot, No

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionHost
Specifies an array that contains the fully qualified domain name (FQDN) of one or more RD Session Host servers that you configure.

```yaml
Type: String[]
Parameter Sets: (All)
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

### Null

## NOTES

## RELATED LINKS

[Add-RDSessionHost](./Add-RDSessionHost.md)

[Get-RDSessionHost](./Get-RDSessionHost.md)

[Remove-RDSessionHost](./Remove-RDSessionHost.md)


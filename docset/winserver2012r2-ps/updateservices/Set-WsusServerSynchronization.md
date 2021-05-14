---
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/updateservices/set-wsusserversynchronization?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WsusServerSynchronization
---

# Set-WsusServerSynchronization

## SYNOPSIS
Sets whether the Windows Server Update Services (WSUS) server synchronizes from Microsoft Update, or an upstream server and the upstream server properties.

## SYNTAX

### SyncFromMU
```
Set-WsusServerSynchronization [-UpdateServer <IUpdateServer>] [-SyncFromMU] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Upstream
```
Set-WsusServerSynchronization [-UpdateServer <IUpdateServer>] -UssServerName <String> [-PortNumber <Int32>]
 [-UseSsl] [-Replica] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WsusServerSynchronization** cmdlet sets whether the Windows Server Update Services (WSUS) server synchronizes from Microsoft Update or an upstream server.
This cmdlet allows the user to specify settings such as the upstream server name, the port number, and whether or not to use Secure Sockets Layer (SSL).

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-WsusServerSynchronization -UssServerName Test -PortNumber 42 -UseSSL
```

This example specifies that the local WSUS Server is to synchronize from another server named Test using port number 42 and the SSL protocol.

### EXAMPLE 2
```
PS C:\> Set-WsusServerSynchronization -SyncFromMU
The Update Server was successfully configured with the following parameters: Synchronize from Microsoft Update
```

This example specifies that the local WSUS Server is to synchronize from Microsoft Update.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PortNumber
Specifies the port number to use to communicate with the upstream WSUS server.

```yaml
Type: Int32
Parameter Sets: Upstream
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replica
Specifies whether the WSUS server is a replica server.

```yaml
Type: SwitchParameter
Parameter Sets: Upstream
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncFromMU
Specifies that the WSUS server synchronizes updates from Microsoft Update.

```yaml
Type: SwitchParameter
Parameter Sets: SyncFromMU
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer
Specifies the object that contains the WSUS server.
This value is obtained by calling the Get-WsusServer cmdlet and piping the resulting IUpdateServer object into this cmdlet.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UseSsl
Specifies that the WSUS server should use Secure Sockets Layer (SSL) via HTTPS to communicate with an upstream server.

```yaml
Type: SwitchParameter
Parameter Sets: Upstream
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -UssServerName
Specifies the name of a local server from which to synchronize updates.

```yaml
Type: String
Parameter Sets: Upstream
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Commands.IUpdateServer
IUpdateServer

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WsusServer](./Get-WsusServer.md)


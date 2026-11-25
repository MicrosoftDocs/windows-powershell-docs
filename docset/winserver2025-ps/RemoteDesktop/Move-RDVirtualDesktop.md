---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/move-rdvirtualdesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-RDVirtualDesktop
---

# Move-RDVirtualDesktop

## SYNOPSIS
Moves a virtual desktop to a new Remote Desktop Virtualization Host (RD Virtualization Host) server.

## SYNTAX

```
Move-RDVirtualDesktop [-SourceHost] <String> [-DestinationHost] <String> [-Name] <String>
 [[-ConnectionBroker] <String>] [[-Credential] <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Move-RDVirtualDesktop** cmdlet moves a virtual desktop to a new Remote Desktop Virtualization Host (RD Virtualization Host) server.

## EXAMPLES

### Example 1: Move a virtual desktop to a new RD Virtualization Host server
```
PS C:\>Enable-WSManCredSSP -Role "Client" -DelegateComputer * -Force
PS C:\> Enable-WSManCredSSP -Role "Server" -DelegateComputer * -Force
PS C:\> $Creds = Get-Credential
PS C:\> Move-RDVirtualDesktop -SourceHost "rdvh-1.contoso.com" -DestinationHost "rdvh-2.contoso.com" -Name "RDS-WKS-A2" -Credential $Creds
```

This example moves a virtual desktop from one RD Virtualization server to another.
The commands run on the RD Connection Broker and move virtual desktops from the source host to the destination host.

The first command enables Credential Security Support Provider (CredSSP) authentication on the destination host.
The **Enable-WSManCredSSP** cmdlet delegates the client credentials to the delegate server.

The second command enables CredSSP authentication on the source host.
The **Enable-WSManCredSSP** cmdlet delegates the server credentials to the delegate server.

The third command gets a credential object based on the user name and password that the user enters.
The command stores the results in the **$Creds** variable.

The fourth command moves the virtual desktop named RDS-WKS-A2 from the source host named rdvh-1.contoso.com to the destination host named rdvh-2.contoso.com.
The command uses the credential object stored in the **$Creds** variable.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object that contains the user credentials for the virtual desktop.
Remote Desktop Services does not require user credentials if you run the cmdlet from the source host.
If you do not specify user credentials for the virtual desktop and you run the cmdlet on a remote host, the server prompts you for credentials.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationHost
Specifies the fully qualified domain name (FQDN) of the new RD Virtualization Host server for the virtual desktop.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a virtual desktop.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceHost
Specifies the fully qualified domain name (FQDN) of the current RD Virtualization Host server for the virtual desktop.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Add-RDVirtualDesktopToCollection](./Add-RDVirtualDesktopToCollection.md)

[Get-RDVirtualDesktop](./Get-RDVirtualDesktop.md)

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)


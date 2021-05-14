---
external help file: RemoteDesktop.psm1-help.xml
Module Name: RDMgmt
online version: https://docs.microsoft.com/powershell/module/rdmgmt/get-rdvirtualdesktopidlecount?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-RDVirtualDesktopIdleCount

## SYNOPSIS
Gets the number of idle virtual desktops on hosts.

## SYNTAX

```
Get-RDVirtualDesktopIdleCount [[-HostServer] <String[]>] [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDVirtualDesktopIdleCount** cmdlet gets the number of idle virtual desktops on one or more hosts.
This cmdlet retruns a value that represents the number of idle virtual desktops from every pool.

An idle virtual desktop is a virtual machine that is in a running state and there is no user logged on to it.
Idle virtual desktops continue to run even if you configured the pool so that the server saves a virtual desktop that is not in use.

## EXAMPLES

### Example 1: Count idle virtual desktops on hosts
```
PS C:\>Get-RDVirtualDesktopIdleCount -HostServer @("rdvh-1.contoso.com","rdvh-2.contoso.com") -ConnectionBroker "rdcb.contoso.com"
```

This command gets the number of idle virtual desktops associated with the connection broker named "rdcb.contoso.com" on the host servers named "rdvh-1.contoso.com" and "rdvh-2.contoso.com".

## PARAMETERS

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
For session collections the host server has the name of the Remote Desktop Session Host (RD  Session Host) server.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-RDVirtualDesktopIdleCount](./Set-RDVirtualDesktopIdleCount.md)

[Get-RDVirtualDesktopCollectionConfiguration](./Get-RDVirtualDesktopCollectionConfiguration.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdvirtualdesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDVirtualDesktop
---

# Get-RDVirtualDesktop

## SYNOPSIS
Gets a list of virtual desktops in the remote desktop deployment.

## SYNTAX

```
Get-RDVirtualDesktop [[-CollectionName] <String[]>] [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDVirtualDesktop** cmdlet gets a list of virtual desktops in the remote desktop deployment.

## EXAMPLES

### Example 1: Retrieve a list of Virtual Desktops
```
PS C:\> Get-RDVirtualDesktop -ConnectionBroker "rdcb.contoso.com" | sort-object VirtualDesktopName
```

This command lists virtual desktops in the collections associated with the connection broker server named rdcb.contoso.com.
The command uses the pipeline operator to send the results to the **Sort-Object** cmdlet, which sorts the objects in order of the VirtualDesktopName property.

### Example 2: Retrieve a list of Virtual Desktops in a Collection
```
PS C:\> Get-RDVirtualDesktop -ConnectionBroker "rdcb.contoso.com" -CollectionName @("Virtual Desktop pool")
```

This command lists virtual desktops in the collection named Virtual Desktop pool that is associated with the connection broker server named rdcb.contoso.com.

## PARAMETERS

### -CollectionName
Specifies an array of names of personal virtual desktop collections.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Move-RDVirtualDesktop](./Move-RDVirtualDesktop.md)

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)


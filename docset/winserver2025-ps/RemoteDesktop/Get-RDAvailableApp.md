---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdavailableapp?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDAvailableApp
---

# Get-RDAvailableApp

## SYNOPSIS
Gets a list of publishable applications from a collection.

## SYNTAX

### Session (Default)
```
Get-RDAvailableApp [-CollectionName] <String> [-ConnectionBroker <String>] [<CommonParameters>]
```

### VirtualDesktop
```
Get-RDAvailableApp [-CollectionName] <String> -VirtualDesktopName <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDAvailableApp** cmdlet gets a list of publishable applications from a collection specified in the **CollectionName** parameter.

## EXAMPLES

### Example 1: Get the list of applications available to publish for a session collection
```
PS C:\> Get-RDAvailableApp -CollectionName "Session Collection" -ConnectionBroker "Rdcb.Contoso.com"
```

This command retrieves a list of the applications available from the session collection named Session Collection, on the RD Connection Broker server named Rdcb.Contoso.com.

### Example 2: Get the list of applications available to publish for a virtual desktop collection
```
PS C:\> Get-RDAvailableApp -CollectionName "Virtual Desktop Pool" -ConnectionBroker "Rdcb.Contoso.com" -VirtualDesktopName "RDS-WKS-A26"
```

This command retrieves a list of the applications available from the session collection named Virtual Desk Pool, on the RD Connection Broker server named Rdcb.Contoso.com.
The cmdlet uses the virtual desktop named RDS-WKS-A26 as the source of a list of applications.

## PARAMETERS

### -CollectionName
Specifies the name of a personal virtual desktop collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### -VirtualDesktopName
Specifies the name of the virtual desktop.
This parameter is required.
The virtual desktop identified here must be a member of the of the collection specified by the **CollectionName** parameter.

```yaml
Type: String
Parameter Sets: VirtualDesktop
Aliases: VMName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.StartMenuApp

## NOTES

## RELATED LINKS


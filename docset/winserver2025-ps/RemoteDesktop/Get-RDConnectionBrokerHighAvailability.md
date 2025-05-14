---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdconnectionbrokerhighavailability?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDConnectionBrokerHighAvailability
---

# Get-RDConnectionBrokerHighAvailability

## SYNOPSIS
Gets high availability settings for the RD Connection Broker server in a Remote Desktop deployment.

## SYNTAX

```
Get-RDConnectionBrokerHighAvailability [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDConnectionBrokerHighAvailability** cmdlet gets high availability settings for the Remote Desktop Connection Broker (RD Connection Broker) server in a Remote Desktop deployment.
The cmdlet displays the following settings:

- ActiveManagementServer.
Current active management server in the highly available RD Connection Broker server list.
- ConnectionBroker.
List of RD Connection Broker servers.
- ClientAccessName.
Client access name for the group of RD Connection Broker servers.
- DatabaseConnectionString.
Database connection string of the central database that stores the configuration.
- DatabaseSecondaryConnectionString.
Database secondary connection string of the central database that stores the configuration.
This setting is displayed if the high availability configuration is on a shared database server.
- DatabaseFilePath.
File path for the database specified by the database connection string.

## EXAMPLES

### Example 1: Get High Availability Settings
```
PS C:\> Get-RDConnectionBrokerHighAvailability -ConnectionBroker "RDCB.Contoso.com"
```

This command gets the high availability settings for the RD Connection Broker server named RDCB.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the RD Connection Broker server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
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

### RDCBHADetails

## NOTES

## RELATED LINKS

[Set-RDConnectionBrokerHighAvailability](./Set-RDConnectionBrokerHighAvailability.md)


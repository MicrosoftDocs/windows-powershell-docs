---
external help file: RemoteDesktop.psm1-help.xml
Module Name: RDMgmt
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/rdmgmt/get-rdconnectionbrokerhighavailability?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### RDCBHADetails

## NOTES

## RELATED LINKS

[Set-RDConnectionBrokerHighAvailability](./Set-RDConnectionBrokerHighAvailability.md)


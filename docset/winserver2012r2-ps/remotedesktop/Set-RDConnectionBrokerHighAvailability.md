---
external help file: RemoteDesktop.psm1-help.xml
Module Name: RDMgmt
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/rdmgmt/set-rdconnectionbrokerhighavailability?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDConnectionBrokerHighAvailability
---

# Set-RDConnectionBrokerHighAvailability

## SYNOPSIS
Sets high availability settings for RD Connection Broker servers for a Remote Desktop deployment.

## SYNTAX

```
Set-RDConnectionBrokerHighAvailability [[-ConnectionBroker] <String>] [-DatabaseConnectionString] <String>
 [-DatabaseFilePath] <String> [-ClientAccessName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDConnectionBrokerHighAvailability** cmdlet sets high availability settings for Remote Desktop Connection Broker (RD Connection Broker) servers for a Remote Desktop deployment.
You can use the Get-RDConnectionBrokerHighAvailability cmdlet to see current settings.

## EXAMPLES

### Example 1: Set high availability settings
```
PS C:\> Set-RDConnectionBrokerHighAvailability -ConnectionBroker "RDCB.Contoso.com" -DatabaseConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=sqlserver.contoso.com;Trusted_Connection=Yes;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment" -DatabaseFilePath "C:\RDFiles\RemoteDesktopDeployment.mdf" -ClientAccessName "RemoteResources.Contoso.com"
```

This command sets high availability settings for an RD Connection Broker server named RDCB.Contoso.com.
The command specifies a database connection string, and includes the path to the database.
The command specifies the client access name as RemoteResources.Contoso.com.

## PARAMETERS

### -ClientAccessName
Specifies a Domain Name System (DNS) name for clients to use to connect to a Remote Desktop deployment.
This is the DNS round robin name that contains fully qualified domain names (FQDNs) of the RD Connection Broker servers.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the RD Connection Broker server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the FQDN of the local computer.

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

### -DatabaseConnectionString
Specifies a connection string for the database that stores the high availability settings.

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

### -DatabaseFilePath
Specifies a path to the database supplied by the **DatabaseConnectionString** parameter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null
None.

## NOTES

## RELATED LINKS

[Get-RDConnectionBrokerHighAvailability](./Get-RDConnectionBrokerHighAvailability.md)


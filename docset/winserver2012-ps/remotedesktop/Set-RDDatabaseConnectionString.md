---
external help file: 
ms.assetid: 01A588C3-6EE1-463F-B907-302499DA3704
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Set-RDDatabaseConnectionString

## SYNOPSIS
Configures the database connection string for the SQL Server database used in high availability environments.

## SYNTAX

```
Set-RDDatabaseConnectionString [-DatabaseConnectionString] <String> [[-ConnectionBroker] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDDatabaseConnectionString** cmdlet configures database connection settings for the SQL Server database used in high availability environments with multiple Remote Desktop Connection Broker (RD Connection Broker) servers.

High availability supports multiple RD Connection Broker roles and servers, and uses SQL Server to store the configuration information for RD Connection Broker servers.

## EXAMPLES

### Example 1: Set a remote desktop database connection string
```
PS C:\> Set-RDDatabaseConnectionString -ConnectionBroker "Rdcb.Contoso.com" -DatabaseConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=Sqlserver.Contoso.com;Trusted_Connection=Yes;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment"
```

This command sets the database connection string for the RD Connection Broker named Rdcb.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the RD Connection Broker server for a remote desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseConnectionString
Specifies the database connection string.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null
None

## NOTES

## RELATED LINKS


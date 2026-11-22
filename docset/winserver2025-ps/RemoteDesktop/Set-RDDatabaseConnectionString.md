---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rddatabaseconnectionstring?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDDatabaseConnectionString
---

# Set-RDDatabaseConnectionString

## SYNOPSIS
Configures the database connection string for the database server used in a high availability environment.

## SYNTAX

```
Set-RDDatabaseConnectionString [[-DatabaseConnectionString] <String>]
 [[-DatabaseSecondaryConnectionString] <String>] [[-ConnectionBroker] <String>] [-RestoreDatabaseConnection]
 [-RestoreDBConnectionOnAllBrokers] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDDatabaseConnectionString** cmdlet configures database connection settings for the database server used in a high availability environment with multiple Remote Desktop Connection Broker (RD Connection Broker) servers.

High availability supports multiple RD Connection Broker roles and servers, and uses a database server to store the configuration information for RD Connection Broker servers.

## EXAMPLES

### Example 1: Set a remote desktop database connection string
```
PS C:\> Set-RDDatabaseConnectionString -ConnectionBroker "Rdcb.Contoso.com" -DatabaseConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=Sqlserver.Contoso.com;Trusted_Connection=Yes;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment"
```

This command sets the database connection string for the RD Connection Broker named Rdcb.Contoso.com.

### Example 2: Set a remote desktop secondary database connection string
```
PS C:\>Set-RDDatabaseConnectionString -ConnectionBroker "Rdcb.Contoso.com" -DatabaseSecondaryConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=Sqlserver.Contoso.com; Uid=admin1;Pwd= OtherPassword!;Encrypt=yes;Connection Timeout=30;;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment"
```

This command sets the secondary database connection string for the RD Connection Broker named Rdcb.Contoso.com.

### Example 3: Update a database connection string on an RD Connection Broker server
```
PS C:\>Set-RDDatabaseConnectionString -ConnectionBroker "Rdcb.Contoso.com" -DatabaseConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=Sqlserver.Contoso.com; Uid=admin1;Pwd= OtherPassword1!;Encrypt=yes;Connection Timeout=30;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment" -DatabaseSecondaryConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=Sqlserver.Contoso.com; Uid=admin2;Pwd= OtherPassword2!;Encrypt=yes;Connection Timeout=30;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment" -RestoreDatabaseConnection
```

This command sets the primary and secondary database connection strings for the RD Connection Broker named Rdcb.Contoso.com after the connection to the database is lost.
Connectivity can be lost if the password expires or if the database administrator changes the connection string.

### Example 4: Update database connection strings on all RD Connection Broker servers
```
PS C:\>Set-RDDatabaseConnectionString -ConnectionBroker "Rdcb.Contoso.com" -DatabaseConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=Sqlserver.Contoso.com; Uid=admin1;Pwd= OtherPassword1!;Encrypt=yes;Connection Timeout=30;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment" -DatabaseSecondaryConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=Sqlserver.Contoso.com; Uid=admin2;Pwd= OtherPassword2!;Encrypt=yes;Connection Timeout=30;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment" -RestoreDatabaseConnection -RestoreDBConnectionOnAllBrokers
```

This command sets the primary and secondary database connection strings for all the RD Connection Broker servers in a deployment after the connection to the database is lost.
Connectivity can be lost if the password expires or if the database administrator changes the connection string.

## PARAMETERS

### -ConnectionBroker
Specifies the RD Connection Broker server for a remote desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseConnectionString
Specifies the database connection string.
The database connection string supports both high availability configurations:

- Dedicated database server.
Uses Windows Authentication to connect to the database.
- Shared database server.
Uses database authentication (such as SQL authentication) with a user name and password to connect to the database.

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

### -DatabaseSecondaryConnectionString
Specifies the secondary database connection string optionally used to support password expiration.
Specify the secondary connection string if the high availability configuration uses a shared database server in which authentication to the database requires a user name and password.

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

### -RestoreDatabaseConnection
Indicates that this operation restores the database connection string(s) when database access is lost for dedicated or shared configurations.

You can use **Set-RDDatabaseConnectionString** on the active management broker to restore the database connection string(s) on the specified broker, or you can specify the *RestoreDBConnectionOnAllBrokers* parameter to restore the database connection string(s) on all RD Connection Brokers in the deployment.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreDBConnectionOnAllBrokers
Indicates that this operation restores the database connection string(s) on all RD Connection Brokers in a deployment to re-establish database connectivity.
If you specify this parameter, you must also specify the *RestoreDatabaseConnection* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
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

[Remove-RDDatabaseConnectionString](./Remove-RDDatabaseConnectionString.md)


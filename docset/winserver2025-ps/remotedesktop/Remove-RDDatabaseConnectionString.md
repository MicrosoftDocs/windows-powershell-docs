---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/remove-rddatabaseconnectionstring?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-RDDatabaseConnectionString
---

# Remove-RDDatabaseConnectionString

## SYNOPSIS
Removes the secondary database connection string for the shared database server in a high availability environment configuration.

## SYNTAX

### DatabaseConnectionString
```
Remove-RDDatabaseConnectionString [-DatabaseConnectionString] [[-ConnectionBroker] <String>] [-Force]
 [<CommonParameters>]
```

### DatabaseSecondaryConnectionString
```
Remove-RDDatabaseConnectionString [-DatabaseSecondaryConnectionString] [[-ConnectionBroker] <String>] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RDDatabaseConnectionString** cmdlet removes the secondary database connection string for the database server in a high availability environment with multiple Remote Desktop Connection Broker (RD Connection Broker) servers.

High availability supports multiple RD Connection Broker roles and servers, and uses a database server to store the configuration information for RD Connection Broker servers.

A secondary database connection string allows for connectivity in the case of an expired password for the primary database connection string.
The secondary database connection string is optional.
You can set this string by using the Set-RDDatabaseConnectionString cmdlet.
You can remove the string by using the current cmdlet.

Currently, you cannot use this cmdlet to remove the primary database connection string.

## EXAMPLES

### Remove a remote desktop database connection string
```
PS C:\> remove-RDDatabaseConnectionString -ConnectionBroker "Rdcb.Contoso.com" -DatabaseConnectionString "DRIVER=SQL Server Native Client 10.0;SERVER=Sqlserver.Contoso.com;Trusted_Connection=Yes;APP=Remote Desktop Services Connection Broker;Database=RemoteDesktopDeployment"
```

This command removes the database connection string for the RD Connection Broker named Rdcb.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the RD Connection Broker server for a remote desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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
This parameter is not currently supported.

```yaml
Type: SwitchParameter
Parameter Sets: DatabaseConnectionString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseSecondaryConnectionString
Indicates that this cmdlet removes the secondary database connection string.

```yaml
Type: SwitchParameter
Parameter Sets: DatabaseSecondaryConnectionString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
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

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Set-RDDatabaseConnectionString](./Set-RDDatabaseConnectionString.md)

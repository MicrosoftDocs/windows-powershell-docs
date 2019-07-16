---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: 
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-RDDatabaseConnectionString
ms.reviewer:
ms.assetid: 3EE6029A-4C7B-40A8-BBB3-77388E8A2AC4
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

### 1:
```

```

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Set-RDDatabaseConnectionString](./Set-RDDatabaseConnectionString.md)


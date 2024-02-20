---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdsessioncollectionconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDSessionCollectionConfiguration
---

# Get-RDSessionCollectionConfiguration

## SYNOPSIS
Gets configuration information for a session collection.

## SYNTAX

### General (Default)
```
Get-RDSessionCollectionConfiguration [-CollectionName] <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### UserGroup
```
Get-RDSessionCollectionConfiguration [-CollectionName] <String> [-UserGroup] [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### Connection
```
Get-RDSessionCollectionConfiguration [-CollectionName] <String> [-Connection] [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### UserProfileDisk
```
Get-RDSessionCollectionConfiguration [-CollectionName] <String> [-UserProfileDisk] [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### Security
```
Get-RDSessionCollectionConfiguration [-CollectionName] <String> [-Security] [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### LoadBalancing
```
Get-RDSessionCollectionConfiguration [-CollectionName] <String> [-LoadBalancing] [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### Client
```
Get-RDSessionCollectionConfiguration [-CollectionName] <String> [-Client] [-ConnectionBroker <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDSessionCollectionConfiguration** cmdlet gets configuration information for a specified session collection.
A session collection consists of one or more Remote Desktop Session Host (RD Session Host) servers.
Users can connect to RD Session Host servers in a session collection to run programs, save files, and use resources on those servers.

You can specify whether to get configuration resources for connection settings, load balancing settings, security settings, or user profile disk settings.
You can also see the domain groups and users authorized to connect to the session.

## EXAMPLES

### Example 1: Get domain groups authorized to connection to a session collection
```
PS C:\> Get-RDSessionCollectionConfiguration -CollectionName "Session Collection 22" -UserGroup -ConnectionBroker "RDCB.Contoso.com"
```

This command gets settings for the session collection named Session Collection 22 that has the RD Connection Broker server named RDCB.Contoso.com.
The command includes the **UserGroup** parameter, therefore the command gets the domain groups authorized to connect to the session collection.

### Example 2: Get connection settings for a session collection
```
PS C:\> Get-RDSessionCollectionConfiguration -CollectionName "Session Collection 22" -Connection -ConnectionBroker "RDCB.Contoso.com"
```

This command gets settings for the session collection named Session Collection 22 that has the RD Connection Broker server named RDCB.Contoso.com.
This command includes the **Connection** parameter, therefore the command gets connection settings.

### Example 3: Get user profile disk settings for a session collection
```
PS C:\> Get-RDSessionCollectionConfiguration -CollectionName "Session Collection 22" -UserProfileDisk -ConnectionBroker "RDCB.Contoso.com"
```

This command gets settings for the session collection named Session Collection 22 that has the RD Connection Broker server named RDCB.Contoso.com.
This command includes the **UserProfileDisk** parameter, therefore the command gets settings for the user profile disk.

### Example 4: Get security settings for a session collection
```
PS C:\> Get-RDSessionCollectionConfiguration -CollectionName "Session Collection 22" -Security -ConnectionBroker "RDCB.Contoso.com"
```

This command gets settings for the session collection named Session Collection 22 that has the RD Connection Broker server named RDCB.Contoso.com.
This command includes the **Security** parameter, therefore the command gets security settings.

### Example 5: Get load balancing settings for a session collection
```
PS C:\> Get-RDSessionCollectionConfiguration -CollectionName "Session Collection 22" -LoadBalancing -ConnectionBroker "RDCB.Contoso.com"
```

This command gets settings for the session collection named Session Collection 22 that has the RD Connection Broker server named RDCB.Contoso.com.
This command includes the **LoadBalancing** parameter, therefore the command gets load balancing settings.

### Example 6: Get client settings for a session collection
```
PS C:\> Get-RDSessionCollectionConfiguration -CollectionName "Session Collection 22" -Client -ConnectionBroker "RDCB.Contoso.com"
```

This command gets settings for the session collection named Session Collection 22 that has the RD Connection Broker server named RDCB.Contoso.com.
This command includes the **Client** parameter, therefore the command gets client settings.

## PARAMETERS

### -Client
Indicates that the cmdlet gets client settings for the session collection, such as those specified by the values of the **ClientDeviceRedirectionOptions**, **ClientPrinterAsDefault**, and **ClientPrinterRedirected** parameters in the Set-RDSessionCollectionConfiguration cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: Client
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionName
Specifies the name of a session collection.

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

### -Connection
Indicates that the cmdlet displays connection settings for the session collection.

```yaml
Type: SwitchParameter
Parameter Sets: Connection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
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

### -LoadBalancing
Indicates that the cmdlet gets load balancing settings for the session collection, such as those set by the **LoadBalancing** parameter in the Set-RDSessionCollectionConfiguration cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: LoadBalancing
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Security
Indicates that the parameter gets the security protocol in use for the session collection.

```yaml
Type: SwitchParameter
Parameter Sets: Security
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserGroup
Indicates that the cmdlet gets the list of domain groups and users authorized to connect to the session.

```yaml
Type: SwitchParameter
Parameter Sets: UserGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserProfileDisk
Indicates that the cmdlet gets settings for the user profile disk for the session collection.

```yaml
Type: SwitchParameter
Parameter Sets: UserProfileDisk
Aliases:

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

### System.Object

## NOTES

## RELATED LINKS

[Set-RDSessionCollectionConfiguration](./Set-RDSessionCollectionConfiguration.md)

[Get-RDSessionCollection](./Get-RDSessionCollection.md)

[New-RDSessionCollection](./New-RDSessionCollection.md)

[Remove-RDSessionCollection](./Remove-RDSessionCollection.md)


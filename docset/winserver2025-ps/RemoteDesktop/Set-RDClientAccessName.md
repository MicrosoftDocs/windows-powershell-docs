---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdclientaccessname?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDClientAccessName
---

# Set-RDClientAccessName

## SYNOPSIS
Sets a DNS name that clients use to connect to a Remote Desktop deployment.

## SYNTAX

```
Set-RDClientAccessName [[-ConnectionBroker] <String>] [-ClientAccessName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDClientAccessName** cmdlet sets a Domain Name System (DNS) name that clients use to connect to a Remote Desktop deployment.
For a deployment that includes a single Remote Desktop Connection Broker (RD Connection Broker) server, provide the fully qualified domain name (FQDN) of the RD Connection Broker server.
For deployment that uses multiple RD Connection Broker servers in an Active/Active cluster, provide the DNS round robin name that contains FQDNs of the RD Connection Broker servers.

## EXAMPLES

### Example 1: Set a client access name
```
PS C:\>Set-RDClientAccessName -ConnectionBroker "RDCB.Contoso.com" -ClientAccessName "RemoteResources.Contoso.com"
```

This command sets the client access name RemoteResources.Contoso.com for the Remote Desktop deployment that has the RD Connection Broker named RDCB.Contoso.com.

## PARAMETERS

### -ClientAccessName
Specifies a DNS name for clients to use to connect to a Remote Desktop deployment.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS


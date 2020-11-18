---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Get-RDAvailableApp
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4BFB5183-9F7C-4D70-AB21-26018218D57D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-RDAvailableApp

## SYNOPSIS
Retrieves a list of publishable applications from a collection.

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
The **Get-RDAvailableApp** cmdlet retrieves a list of publishable applications from a collection specified in the **CollectionName** parameter.

## EXAMPLES

### Example 1: Retrieve the list of applications available to be published for a Session Collection
```
PS C:\> Get-RDAvailableApp -CollectionName "Session Collection" -ConnectionBroker "Rdcb.Contoso.com"
```

This command retrieves a list of the applications available from the session collection named Session Collection, on the RD Connection Broker server named Rdcb.Contoso.com.

### Example 2: Retrieve the list of applications available to be published for a Virtual Desktop Collection
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.StartMenuApp

## NOTES

## RELATED LINKS


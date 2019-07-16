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
title: Set-RDActiveManagementServer
ms.reviewer:
ms.assetid: 973B1B3B-5265-4359-8360-F481A4C450B7
---

# Set-RDActiveManagementServer

## SYNOPSIS
Sets the active Remote Desktop Connection Broker  server, or management server, in a remote desktop deployment.

## SYNTAX

```
Set-RDActiveManagementServer [-ManagementServer] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDActiveManagementServer** cmdlet sets the active Remote Desktop Connection Broker (RD Connection Broker) server in a remote desktop deployment.

This server runs the Remote Desktop Management Server (RDMS) service, which belongs in a high availability group to ensure uninterrupted access.
The Remote Desktop Management Server service configures the deployment and deployment properties, creates and configures collections, and provisions virtual machines.

## EXAMPLES

### Example 1: Set the active management server for a remote desktop deployment
```
PS C:\> Set-RDActiveManagementServer -ManagementServer "Rdcb.Contoso.com"
```

This command sets the active management server for the remote desktop.

## PARAMETERS

### -ManagementServer
Specifies the name of a server that acts as the active RD Connection Broker for a remote desktop deployment.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null
None

## NOTES

## RELATED LINKS


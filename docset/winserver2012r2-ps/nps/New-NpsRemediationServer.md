---
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: Nps
online version: 
schema: 2.0.0
title: New-NpsRemediationServer
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 15428631-C8D6-4BA6-A9B4-7795384C3015
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-NpsRemediationServer

## SYNOPSIS
Creates a remediation server.

## SYNTAX

```
New-NpsRemediationServer [-RemediationServerGroup] <String> [-Address] <String> [-Name <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NpsRemediationServer** cmdlet creates a remediation server in a remediation server group that you specify.

In Network Access Protection (NAP), the network policies on the Microsoft Windows Network Policy Server (NPS) use remediation to enforce NAP for clients whose health state does not comply with policy requirements and to bring those clients into a compliant state.
Remediation servers provide the resources that clients need to become compliant including the client management point, the software update point, or distribution points that contain software updates.

## EXAMPLES

### Example 1: Add a new remediation server
```
PS C:\>New-NpsRemediationServer -Address "Server1.adatum.com" -Name "Seattle Remediation Server" -RemediationServerGroup "Servers1"
```

This command adds a remediation server with the FQDN Server1.adatum.com to a remediation server group named Servers1.
The server name is Seattle Remediation Server.

## PARAMETERS

### -Address
Specifies the fully qualified domain name (FQDN) or IP address of the remediation server to add.
The address must be unique.

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

### -Name
Specifies the name of the remediation server to add.

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

### -RemediationServerGroup
Specifies the name of the remediation server group to which you add the server.

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

### NpsRemediationServer

## NOTES

## RELATED LINKS

[Get-NpsRemediationServer](./Get-NpsRemediationServer.md)

[Get-NpsRemediationServerGroup](./Get-NpsRemediationServerGroup.md)

[New-NpsRemediationServerGroup](./New-NpsRemediationServerGroup.md)

[Remove-NpsRemediationServer](./Remove-NpsRemediationServer.md)

[Remove-NpsRemediationServerGroup](./Remove-NpsRemediationServerGroup.md)


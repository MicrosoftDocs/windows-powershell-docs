---
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: Nps
online version: 
schema: 2.0.0
title: Remove-NpsRemediationServer
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: FD3EB5BB-759E-4503-A901-F23998B41DC0
ms.author: kenwith
ms.reviewer: brianlic
---

# Remove-NpsRemediationServer

## SYNOPSIS
Removes a remediation server from a remediation server group.

## SYNTAX

```
Remove-NpsRemediationServer [-RemediationServerGroup] <String> [-Address] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NpsRemediationServer** cmdlet removes a remediation server from a remediation server group that you specify.

In Network Access Protection (NAP), the network policies on the Microsoft Windows Network Policy Server (NPS) use remediation to enforce NAP for clients whose health state does not comply with policy requirements and to bring those clients into a compliant state.
Remediation servers provide the resources that clients need to become compliant including the client management point, the software update point, or distribution points that contain software updates.
For more information about remediation, see NAP Configuration Overviewhttp://technet.microsoft.com/library/dd125319(v=ws.10).aspx (http://technet.microsoft.com/library/dd125319(v=ws.10).aspx) on TechNet.

## EXAMPLES

### Example 1: Remove a remediation server
```
PS C:\>Remove-NpsRemediationServer -Address "Server1.adatum.com" -RemediationServerGroup "Servers1"
```

This command removes the remediation server with the FQDN Server1.adatum.com from the remediation server group named Servers1.

## PARAMETERS

### -Address
Specifies the fully qualified domain name (FQDN) or IP address of the remediation server.
If more than one server with the address specified exists, the cmdlet removes all of them.

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

### -RemediationServerGroup
Specifies the name of the remediation server group from which you delete a server.

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

### None

## NOTES

## RELATED LINKS

[Get-NpsRemediationServer](./Get-NpsRemediationServer.md)

[Get-NpsRemediationServerGroup](./Get-NpsRemediationServerGroup.md)

[New-NpsRemediationServer](./New-NpsRemediationServer.md)

[New-NpsRemediationServerGroup](./New-NpsRemediationServerGroup.md)

[Remove-NpsRemediationServerGroup](./Remove-NpsRemediationServerGroup.md)


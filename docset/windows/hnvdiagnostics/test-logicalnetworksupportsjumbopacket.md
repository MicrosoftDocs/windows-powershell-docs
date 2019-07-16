---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Test-LogicalNetworkSupportsJumboPacket-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Test-LogicalNetworkSupportsJumboPacket
ms.reviewer:
ms.assetid: B402E566-55FB-4C7E-89B6-7F5C344FD544
---

# Test-LogicalNetworkSupportsJumboPacket

## SYNOPSIS
Tests whether a jumbo packet can be sent between two nodes.

## SYNTAX

```
Test-LogicalNetworkSupportsJumboPacket [-SourceHost] <String> [-DestinationHost] <String>
 [[-SourceHostCreds] <PSCredential>] [[-DestinationHostCreds] <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-LogicalNetworkSupportsJumboPacket** cmdlet tests whether a jumbo packet can be sent between two nodes.

## EXAMPLES

### Example 1: Test a jumbo packet
```
PS C:\> $cred = Get-Credential
Test-LogicalNetworkSupportsJumboPacket -SourceHost "localhost" -SourceHostCreds $cred -DestinationHost "1.1.1.1" -DestinationHostCreds $cred
```

The first command gets the user's credentials, and then stores them in the $cred variable.

The second command tests a jumbo packet between the specified source and destination hosts.

## PARAMETERS

### -DestinationHost
Specifies the destination IP address or fully qualified domain name (FQDN).

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

### -DestinationHostCreds
Specifies the credentials to use on the destination host.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceHost
Specifies the source IP address or FQDN.

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

### -SourceHostCreds
Specifies the credentials to use on the source host.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS


---
author: Kateyanne
description:
external help file: RemoteDesktop.psm1-help.xml
manager: jasgro
Module Name: RDMgmt
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/rdmgmt/new-rdsessioncollection?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-RDSessionCollection
---

# New-RDSessionCollection

## SYNOPSIS
Creates a session collection of RD Session Host servers.

## SYNTAX

```
New-RDSessionCollection [-CollectionName] <String> [-CollectionDescription <String>] -SessionHost <String[]>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-RDSessionCollection** cmdlet creates a session collection that consists of one or more Remote Desktop Session Host (RD Session Host) servers.
Users can connect to RD Session Host servers in a session collection to run programs, save files, and use resources on those servers.

## EXAMPLES

### Example 1: Create a session collection
```
PS C:\> New-RDSessionCollection -CollectionName "Session Collection 02" -SessionHost @("RDSH01.Contoso.com"," RDSH02.Contoso.com") -CollectionDescription "Session collection for West office hosts." -ConnectionBroker "RDCB.Contoso.com"
```

This command creates a session collection named Session Collection 02 in the Remote Desktop deployment that has the RD Connection Broker server named RDCB.Contoso.com.
The collection includes the RD Session Host servers named RDSH01.Contoso.com and RDSH02.Contoso.com.
The command specifies a description of the new collection.

## PARAMETERS

### -CollectionDescription
Specifies a description for the collection.

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

### -CollectionName
Specifies a name for the session collection.

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

### -SessionHost
Specifies an array of RD Session Host servers to include in the session collection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

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

### Microsoft.RemoteDesktopServices.Management.RDSessionCollection

## NOTES

## RELATED LINKS

[Get-RDSessionCollection](./Get-RDSessionCollection.md)

[Remove-RDSessionCollection](./Remove-RDSessionCollection.md)


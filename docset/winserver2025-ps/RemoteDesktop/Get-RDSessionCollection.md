---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdsessioncollection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDSessionCollection
---

# Get-RDSessionCollection

## SYNOPSIS
Gets session collections in a Remote Desktop deployment.

## SYNTAX

```
Get-RDSessionCollection [[-CollectionName] <String>] [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDSessionCollection** cmdlet gets session collections in a Remote Desktop deployment.
A session collection consists of one or more Remote Desktop Session Host (RD Session Host) servers.
Users can connect to RD Session Host servers in a session collection to run programs, save files, and use resources on those servers.
The user needs to be a member of the local computer Administrator group to run this command.

## EXAMPLES

### Example1: Get a list of the Session Collections in the Remote Desktop Deployment
```
PS C:\> Get-RDSessionCollection -CollectionName "Session Collection" -ConnectionBroker "RDCB.Contoso.com"
```

This command gets the collection named Session Collection in the deployment that has the RD Connection Broker named RDCB.Contoso.com.

## PARAMETERS

### -CollectionName
Specifies the name of a session collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.RDSessionCollection

## NOTES

## RELATED LINKS

[New-RDSessionCollection](./New-RDSessionCollection.md)

[Remove-RDSessionCollection](./Remove-RDSessionCollection.md)


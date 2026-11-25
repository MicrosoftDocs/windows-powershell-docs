---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdusersession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDUserSession
---

# Get-RDUserSession

## SYNOPSIS
Gets a list of all user sessions in a collection or in a Remote Desktop deployment.

## SYNTAX

```
Get-RDUserSession [[-CollectionName] <String[]>] [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDUserSession** cmdlet gets a list of all user sessions in a collection or in a Remote Desktop deployment.

## EXAMPLES

### Example 1: Retrieve a list of user sessions in a collection
```
PS C:\> Get-RDUserSession -ConnectionBroker "rdcb.contoso.com"
```

This command lists user sessions in a collection that is associated with the RD Connection Broker server named rdcb.contoso.com.

### Example 2: Retrieve a list of user sessions in multiple collections
```
PS C:\> Get-RDUserSession -ConnectionBroker "rdcb.contoso.com" -CollectionName @("Session Collection","Virtual Desktop Collection")
```

This command lists user sessions in the collections named Session Collection and Virtual Desktop Collection.
The cmdlet associates these collections with the RD  Connection Broker server named rdcb.contoso.com.

## PARAMETERS

### -CollectionName
Specifies an array that contains the name of the virtual desktop collection that contains the user sessions.
If this parameter does not appear, the cmdlet returns all user sessions across all virtual desktop collections.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
Remote users connect to this server to obtain views of available firstref_server_7 RemoteApp programs, session-based desktops, and virtual desktops.
If this parameter does not appear, the default value is the fully qualified domain name (FQDN) of the local host.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.RDUserSession

## NOTES

## RELATED LINKS


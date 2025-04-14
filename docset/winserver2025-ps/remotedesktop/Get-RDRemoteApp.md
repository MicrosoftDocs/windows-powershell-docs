---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdremoteapp?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDRemoteApp
---

# Get-RDRemoteApp

## SYNOPSIS
Gets RemoteApp programs in a Remote Desktop deployment.

## SYNTAX

```
Get-RDRemoteApp [[-CollectionName] <String>] [[-Alias] <String>] [-DisplayName <String[]>]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDRemoteApp** cmdlet gets Windows Server 2012 RemoteApp programs in a Remote Desktop deployment.
You can specify a collection name, an alias, or one or more display names.

RemoteApp allows Remote Desktop Services (RDS) to run a program remotely that appears as if it runs locally on a client computer.
A RemoteApp program runs in its own resizable window and has its own entry on the taskbar.

## EXAMPLES

### Example 1: Get RemoteApp programs for a collection
```
PS C:\> Get-RDRemoteApp -CollectionName "Session Collection"
```

This command gets RemoteApp programs for the collection named Session Collection, as specified by the **CollectionName** parameter.

### Example 2: Get RemoteApp programs by using a display name
```
PS C:\> Get-RDRemoteApp -DisplayName Note*
```

This command gets RemoteApp programs that begin with the string Note.

## PARAMETERS

### -Alias
Specifies an alias for a RemoteApp program.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CollectionName
Specifies the name of a personal virtual desktop collection or session collection.

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

### -DisplayName
Specifies an array of names to display to users for RemoteApp programs.
You can use a wildcard character.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.RemoteApp

## NOTES

## RELATED LINKS

[New-RDRemoteApp](./New-RDRemoteApp.md)

[Remove-RDRemoteApp](./Remove-RDRemoteApp.md)

[Set-RDRemoteApp](./Set-RDRemoteApp.md)


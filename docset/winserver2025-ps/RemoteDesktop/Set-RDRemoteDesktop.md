---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdremotedesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDRemoteDesktop
---

# Set-RDRemoteDesktop

## SYNOPSIS
Changes whether to publish a Remote Desktop to a collection.

## SYNTAX

```
Set-RDRemoteDesktop [-CollectionName] <String> [-ShowInWebAccess] <Boolean> [-ConnectionBroker <String>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDRemoteDesktop** cmdlet changes whether to publish a Remote Desktop connection to a collection.

When you publish a Remote Desktop connection, the Remote Desktop Web Access (RD Web Access) server displays the Remote Desktop connection for the collection defined by the **CollectionName** parameter.
RemoteApp and Desktop Connections that the user subscribes to also display published Remote Desktop connections.

You can publish either RemoteApps or a Remote Desktop connection to a collection, but not both.
Therefore, if you publish a Remote Desktop connection by using this cmdlet, it unpublishes any published RemoteApps.

## EXAMPLES

### Example 1: Publish a Remote Desktop
```
PS C:\> Set-RDRemoteDesktop -CollectionName "Session Collection" -ShowInWebAccess $True
```

This command publishes a Remote Desktop to the collection named Session Collection.
The **ShowInWebAccess** parameter has a value of $True, therefore the collection appears in RD Web Access.
RemoteApp and Desktop Connections that the user subscribes to also display the collection.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowInWebAccess
Specifies whether to publish a Remote Desktop connection.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDRemoteDesktop](./Get-RDRemoteDesktop.md)


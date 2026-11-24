---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/get-iscsitargetserversetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IscsiTargetServerSetting
---

# Get-IscsiTargetServerSetting

## SYNOPSIS
Gets the global settings or common configurations for iSCSI target, virtual disk or snapshots.

## SYNTAX

```
Get-IscsiTargetServerSetting [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IscsiTargetServerSetting** cmdlet gets the global settings or common configurations for iSCSI targets, virtual disks or snapshots.

## EXAMPLES

### Example 1: Get portal entries for the local computer
```
PS C:\> Get-IscsiTargetServerSetting
ComputerName                            Version                                 Portals
------------                            -------                                 -------
fssvr.contoso.com                       6.3.9600                                {+172.21.0.1:3260, ...
```

This example gets all of the portal entries of the local server.

## PARAMETERS

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer.

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the credentials when connecting to a remote computer.

```yaml
Type: PSCredential
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Set-IscsiTargetServerSetting](./Set-IscsiTargetServerSetting.md)


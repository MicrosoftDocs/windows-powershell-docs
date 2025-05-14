---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdvirtualdesktopcollectionconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDVirtualDesktopCollectionConfiguration
---

# Get-RDVirtualDesktopCollectionConfiguration

## SYNOPSIS
Gets configuration details of a virtual desktop collection.

## SYNTAX

### General (Default)
```
Get-RDVirtualDesktopCollectionConfiguration [-CollectionName] <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### VirtualDesktopConfiguration
```
Get-RDVirtualDesktopCollectionConfiguration [-CollectionName] <String> [-VirtualDesktopConfiguration]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

### UserGroups
```
Get-RDVirtualDesktopCollectionConfiguration [-CollectionName] <String> [-UserGroups]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

### Client
```
Get-RDVirtualDesktopCollectionConfiguration [-CollectionName] <String> [-Client] [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### UserProfileDisks
```
Get-RDVirtualDesktopCollectionConfiguration [-CollectionName] <String> [-UserProfileDisks]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDVirtualDesktopCollectionConfiguration** gets configuration details of a virtual desktop collection.

## EXAMPLES

### Example 1: Get configuration settings for virtual desktops in a collection
```
PS C:\> Get-RDVirtualDesktopCollectionConfiguration -ConnectionBroker "rdcb.contoso.com" -CollectionName "Virtual Desktop Pool" -VirtualDesktopConfiguration
```

This command gets the configuration settings for the virtual desktops in the collection named Virtual Desktop Pool that is associated with the RD Connection Broker server named rdcb.contoso.com.

### Example 2: Get user profile disk settings for a virtual desktop collection
```
PS C:\> Get-RDVirtualDesktopCollectionConfiguration -ConnectionBroker "rdcb.contoso.com" -CollectionName "Virtual Desktop Pool" -UserProfileDisks
```

This command gets the user profile disk settings for the virtual desktop collection named Virtual Desktop Pool that is associated with the RD Connection Broker server named rdcb.contoso.com.

## PARAMETERS

### -Client
Indicates that this cmdlet gets Remote Desktop Protocol (RDP) settings for virtual desktops in the collection.

```yaml
Type: SwitchParameter
Parameter Sets: Client
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionName
Specifies the name of a virtual desktop collection.

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
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
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

### -UserGroups
Indicates that the cmdlet gets a list of domain groups and users that are authorized to connect to the collection.

```yaml
Type: SwitchParameter
Parameter Sets: UserGroups
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserProfileDisks
Indicates that the cmdlet gets a list of user profile disk settings for the collection.

```yaml
Type: SwitchParameter
Parameter Sets: UserProfileDisks
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopConfiguration
Indicates that the cmdlet gets configuration settings for virtual desktops in the collection.

```yaml
Type: SwitchParameter
Parameter Sets: VirtualDesktopConfiguration
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-RDVirtualDesktopCollectionConfiguration](./Set-RDVirtualDesktopCollectionConfiguration.md)

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)

[Remove-RDVirtualDesktopCollection](./Remove-RDVirtualDesktopCollection.md)


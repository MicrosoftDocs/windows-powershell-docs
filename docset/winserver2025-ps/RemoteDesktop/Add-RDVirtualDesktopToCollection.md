---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/add-rdvirtualdesktoptocollection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-RDVirtualDesktopToCollection
---

# Add-RDVirtualDesktopToCollection

## SYNOPSIS
Adds virtual desktops to a virtual desktop collection.

## SYNTAX

### PooledMgd (Default)
```
Add-RDVirtualDesktopToCollection [-CollectionName] <String> -VirtualDesktopAllocation <Hashtable>
 [-VirtualDesktopPasswordAge <Int32>] [-ConnectionBroker <String>] [<CommonParameters>]
```

### UnManaged
```
Add-RDVirtualDesktopToCollection [-CollectionName] <String> -VirtualDesktopName <String[]>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

### PersonalMgd
```
Add-RDVirtualDesktopToCollection [-CollectionName] <String> -VirtualDesktopAllocation <Hashtable>
 [-VirtualDesktopTemplateName <String>] [-VirtualDesktopTemplateHostServer <String>]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-RDVirtualDesktopToCollection** cmdlet adds one or more virtual desktops to a virtual desktop collection.
You can use this cmdlet to add virtual desktops to personal virtual desktop collections, managed pooled virtual desktop collections, and unmanaged pooled virtual desktop collections.

## EXAMPLES

### Example 1: Add virtual desktops to a virtual desktop collection on an RD Connection Broker
```
PS C:\> Add-RDVirtualDesktopToCollection -ConnectionBroker "rdcb.contoso.com" -CollectionName "Virtual Desktop Pool" -VirtualDesktopAllocation @{"RDS-WKS-A27.vdi.contoso.com"=1;"RDS-WKS-A28.vdi.contoso.com"=2} -VirtualDesktopPasswordAge 31
```

This command adds virtual desktops to the managed pooled virtual desktop collection named Virtual Desktop Pool that is associated with the RD Connection Broker server named rdcb.contoso.com.
The **VirtualDesktopAllocation** parameter specifies that one virtual desktop is created on the host servers named RDS-WKS-A27.vdi.contoso.com and two virtual desktops are created on the host server named RDS-WKS-A28.vdi.contoso.com.
The command specifies that after 31 days the server enforces a password update for the virtual desktops.

## PARAMETERS

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

### -VirtualDesktopAllocation
Specifies a collection of values (key/value pair) that allocate virtual desktops to Remote Desktop Virtualization (RD Virtualization Host) servers.

```yaml
Type: Hashtable
Parameter Sets: PooledMgd, PersonalMgd
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies an array of names of a virtual desktops.

```yaml
Type: String[]
Parameter Sets: UnManaged
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopPasswordAge
Specifies the number of days after which the server enforces a password update.

```yaml
Type: Int32
Parameter Sets: PooledMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopTemplateHostServer
Specifies the fully qualified domain name (FQDN) of the server where the virtual desktop template associated with the collection is stored.

```yaml
Type: String
Parameter Sets: PersonalMgd
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopTemplateName
Specifies a descriptive name for the virtual desktop template.

```yaml
Type: String
Parameter Sets: PersonalMgd
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

### System.Object

## NOTES

## RELATED LINKS

[Remove-RDVirtualDesktopFromCollection](./Remove-RDVirtualDesktopFromCollection.md)

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)


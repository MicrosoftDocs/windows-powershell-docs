---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdpersonalvirtualdesktopassignment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDPersonalVirtualDesktopAssignment
---

# Set-RDPersonalVirtualDesktopAssignment

## SYNOPSIS
Creates an association between a personal virtual desktop and a user account.

## SYNTAX

```
Set-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> -User <String> -VirtualDesktopName <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDPersonalVirtualDesktopAssignment** cmdlet creates an association between a personal virtual desktop and a user account.

## EXAMPLES

### Example 1: Create an association between a user and a personal virtual desktop
```
PS C:\>Set-RDPersonalVirtualDesktopAssignment -CollectionName "Virtual Desktop Collection" -User "CONTOSO\sarahjones" -PersonalVirtualDesktop "PVD-21"
```

This command associates a user with a personal virtual desktop.

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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### -User
Specifies the user account to associate with the personal virtual desktop, in DOMAIN\User format.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of the virtual desktop.
This parameter is required.
The virtual desktop identified here must be a member of the collection that the **CollectionName** parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Export-RDPersonalVirtualDesktopAssignment](./Export-RDPersonalVirtualDesktopAssignment.md)

[Get-RDPersonalVirtualDesktopAssignment](./Get-RDPersonalVirtualDesktopAssignment.md)

[Import-RDPersonalVirtualDesktopAssignment](./Import-RDPersonalVirtualDesktopAssignment.md)

[Remove-RDPersonalVirtualDesktopAssignment](./Remove-RDPersonalVirtualDesktopAssignment.md)


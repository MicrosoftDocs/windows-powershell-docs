---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/remove-rdpersonalvirtualdesktopassignment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-RDPersonalVirtualDesktopAssignment
---

# Remove-RDPersonalVirtualDesktopAssignment

## SYNOPSIS
Removes the association between a personal virtual desktop and a user.

## SYNTAX

### RemoveByUser (Default)
```powershell
Remove-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> [-User] <String>
 [-ConnectionBroker <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByDesktop
```powershell
Remove-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> [-VirtualDesktopName] <String>
 [-ConnectionBroker <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RDPersonalVirtualDesktopAssignment** cmdlet removes an existing association between a personal virtual desktop and a user.
This removal makes the virtual desktop available for another user.

## EXAMPLES

### Example 1: Remove a personal virtual desktop assignment by user
```powershell
PS C:\>Remove-RDPersonalVirtualDesktopAssignment -CollectionName "Virtual Desktop Collection" -User "CONTOSO\sarahjones"
```

This command removes a personal virtual desktop assignment by user.

### Example 2: Remove a personal virtual desktop assignment virtual desktop name
```powershell
PS C:\>Remove-RDPersonalVirtualDesktopAssignment -CollectionName "Virtual Desktop Collection" -VirtualDesktopName "PVD-12"
```

This command removes a personal virtual desktop assignment by virtual desktop name.


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

### -User
Specifies the user account to remove, in DOMAIN\User format.

```yaml
Type: String
Parameter Sets: RemoveByUser
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of the virtual desktop.
This parameter is required.
The virtual desktop identified here must be a member of the collection that the *CollectionName* parameter specifies.

```yaml
Type: String
Parameter Sets: RemoveByDesktop
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

### System.Object

## NOTES

## RELATED LINKS

[Export-RDPersonalVirtualDesktopAssignment](./Export-RDPersonalVirtualDesktopAssignment.md)

[Get-RDPersonalVirtualDesktopAssignment](./Get-RDPersonalVirtualDesktopAssignment.md)

[Import-RDPersonalVirtualDesktopAssignment](./Import-RDPersonalVirtualDesktopAssignment.md)

[Set-RDPersonalVirtualDesktopAssignment](./Set-RDPersonalVirtualDesktopAssignment.md)


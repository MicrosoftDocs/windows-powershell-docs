---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/update-rdvirtualdesktopcollection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-RDVirtualDesktopCollection
---

# Update-RDVirtualDesktopCollection

## SYNOPSIS
Associates a virtual desktop collection with a new virtual desktop template.

## SYNTAX

### Now (Default)
```
Update-RDVirtualDesktopCollection [-CollectionName] <String> -VirtualDesktopTemplateName <String>
 -VirtualDesktopTemplateHostServer <String> [-DisableVirtualDesktopRollback]
 [-VirtualDesktopPasswordAge <Int32>] [-ConnectionBroker <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### OnUserLogoff
```
Update-RDVirtualDesktopCollection [-CollectionName] <String> -VirtualDesktopTemplateName <String>
 -VirtualDesktopTemplateHostServer <String> [-DisableVirtualDesktopRollback]
 [-VirtualDesktopPasswordAge <Int32>] [-ConnectionBroker <String>] [-Force] -StartTime <DateTime>
 -ForceLogoffTime <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### OnSchedule
```
Update-RDVirtualDesktopCollection [-CollectionName] <String> -VirtualDesktopTemplateName <String>
 -VirtualDesktopTemplateHostServer <String> [-DisableVirtualDesktopRollback]
 [-VirtualDesktopPasswordAge <Int32>] [-ConnectionBroker <String>] [-Force] -ForceLogoffTime <DateTime>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-RDVirtualDesktopCollection** cmdlet associates an existing virtual desktop collection with a new virtual desktop template.

## EXAMPLES

### Example 1: Update a virtual desktop collection
```
PS C:\>Update-RDVirtualDesktopCollection -CollectionName "Virtual Desktop pool" VirtualDesktopTemplateName "RDS-Template" -VirtualDesktopTemplateHostServer "rdvh-1.contoso.com" -ForceLogoffTime 12:00am -DisableVirtualDesktopRollback -VirtualDesktopPasswordAge 31 -ConnectionBroker "rdcb.contoso.com"
```

This command updates the virtual desktop collection named Virtual Desktop pool with the virtual desktop template named RDS-Template on the host server named rdvh-1.contoso.com.

The command specifies that the server ends the session if the update operation is still running at 12:00am.
The command disables the rollback of a virtual desktop deployment and specifies that the server forces a password update for the computer account for a virtual desktop after 31 days.

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

### -DisableVirtualDesktopRollback
Indicates that the server prevents the rollback of a virtual desktop deployment.

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

### -ForceLogoffTime
Specifies a date and time by which the server ends the session if the operation is still running.

```yaml
Type: DateTime
Parameter Sets: OnUserLogoff, OnSchedule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies a date and time to start the operation.

```yaml
Type: DateTime
Parameter Sets: OnUserLogoff
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopPasswordAge
Specifies the number of days after which the server forces a password update for the computer account.

```yaml
Type: Int32
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopTemplateName
Specifies a descriptive name for the virtual desktop template.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)

[New-RDVirtualDesktopCollection](./New-RDVirtualDesktopCollection.md)

[Remove-RDVirtualDesktopCollection](./Remove-RDVirtualDesktopCollection.md)


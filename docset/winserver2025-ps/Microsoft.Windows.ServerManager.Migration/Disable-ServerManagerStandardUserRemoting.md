---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ServerManager-help.xml
Module Name: Microsoft.Windows.ServerManager.Migration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.servermanager.migration/disable-servermanagerstandarduserremoting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ServerManagerStandardUserRemoting
---

# Disable-ServerManagerStandardUserRemoting

## SYNOPSIS
Disables access for specified standard users to event, service, performance counter, and role and feature inventory data that is collected by Server Manager for a server.

## SYNTAX

```
Disable-ServerManagerStandardUserRemoting [-User] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-ServerManagerStandardUserRemoting** cmdlet disables access for one or more standard, non-Administrator users to event, service, performance counter, and role and feature inventory data for a server that you are managing by using Server Manager.
This cmdlet performs the opposite action, for specified users, of the Enable-ServerManagerStandardUserRemoting cmdlet.

The cmdlet restores the default, administrator-only access to this data, and must be run locally on the server that is being managed by using Server Manager.
The cmdlet works by performing the following actions:

- Deletes access rights for specified standard users to the root\cimv2 namespace on the local server (for access to role and feature inventory information).
- Removes specified standard users from user groups (Remote Management Users, Event Log Readers, and Performance Log Readers) that allow remote access to event and performance counter logs on the local server.
- Removes access rights in the Service Control Manager for specified standard users who have access to the status of services on the local server.

## EXAMPLES

### Example 1: Disable access to event, performance counter, service status and role and feature inventory data for a user
```
PS C:\> Disable-ServerManagerStandardUserRemoting -User "PattiFul"
```

This command disables access to event, performance counter, service status, and role and feature inventory data for a server that is being managed by using either a local or remote Server Manager console, and for which there is a standard user named PattiFul.

### Example 2: Simulate the outcome of disabling access to event, performance counter, service status and role and feature inventory data for a user
```
PS C:\> Disable-ServerManagerStandardUserRemoting -User "EvanNar" -WhatIf
```

This command views the outcome of running a command to deny a standard user named EvanNar access to event, performance counter, service status, and role and feature inventory data for a server that is being managed by using the Server Manager console running on either the local or a remote computer.
Because the *WhatIf* parameter is used, the command actions are not carried out.

### Example 3: Disable access to event, performance counter, service status and role and feature inventory data for a user
```
PS C:\> Disable-ServerManagerStandardUserRemoting -User "PattiFul" -Confirm
```

This command denies a standard user named PattiFul access to event, performance counter, service status, and role and feature inventory data for a server that is being managed by using the Server Manager console running on either the local or a remote computer.
Because the *Confirm* parameter is used, the command prompts for confirmation before performing the action.

## PARAMETERS

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
Specifies an array of user account names of standard users who runs Server Manager, and no longer requires access to event, performance counter, service, and role and feature inventory data for a server that is being managed by using either a local or remote Server Manager console.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

## NOTES

## RELATED LINKS

[Get-WindowsFeature](./Get-WindowsFeature.md)

[Install-WindowsFeature](./Install-WindowsFeature.md)

[Uninstall-WindowsFeature](./Uninstall-WindowsFeature.md)

[Enable-ServerManagerStandardUserRemoting](./Enable-ServerManagerStandardUserRemoting.md)


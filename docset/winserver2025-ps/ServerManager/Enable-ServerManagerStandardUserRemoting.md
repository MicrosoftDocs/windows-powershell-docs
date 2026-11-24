---
description: Provides one or more standard, non-Administrator users access to event, service, performance counter, and role and feature inventory data for a server that you are managing by using Server Manager.
external help file: ServerManager-help.xml
Module Name: ServerManager
ms.date: 09/08/2021
online version: https://learn.microsoft.com/powershell/module/servermanager/enable-servermanagerstandarduserremoting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ServerManagerStandardUserRemoting
---

# Enable-ServerManagerStandardUserRemoting

## SYNOPSIS

Provides one or more standard, non-Administrator users access to event, service, performance
counter, and role and feature inventory data for a server that you are managing by using Server
Manager.

## SYNTAX

```
Enable-ServerManagerStandardUserRemoting [-User] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Provides one or more standard, non-Administrator users access to event, service, performance
counter, and role and feature inventory data for a server that you are managing, either locally or
remotely, by using Server Manager. The cmdlet must be run locally on the server that you are
managing by using Server Manager. The cmdlet works by performing the following actions:

- Adds access rights for specified standard users to the root\cimv2 namespace on the local server
  (for access to role and feature inventory information).

- Adds specified standard users to required user groups (Remote Management Users, Event Log Readers,
  and Performance Log Readers) that allow remote access to event and performance counter logs on the
  managed server.

- Changes access rights in the Service Control Manager to allow specified standard users remote
  access to the status of services on the managed server.

This cmdlet does not provide standard users access to bpa (BPA) results, or allow standard users to
run BPA scans. Aside from the preceding list of changes, this cmdlet provides no additional access
that a standard user does not already have, by default, on managed servers.

Running this cmdlet has security implications for your network environment because it grants
specified non-Administrator users access rights to information that, by default, is restricted to
members of the Administrators group on the local computer. The cmdlet provides access to other WMI
providers in the root\cimv2 namespace, but only those providers that can be used by standard users.
We recommend that you run this cmdlet only when you must add a specific standard user to the users
who require access to remote server data by using Server Manager. Additionally, you should promptly
run `Disable-ServerManagerStandardUserRemoting` to deny this access to users as soon as they no
longer require it.

## EXAMPLES

### Example 1

```powershell
Enable-ServerManagerStandardUserRemoting -User JennyL
```

In this example, the administrator gives a standard user named `JennyL` access to event, performance
counter, service status, and role and feature inventory data on a server that is being managed,
either locally or remotely, by using Server Manager.

### Example 2

```powershell
Enable-ServerManagerStandardUserRemoting -User JennyL -WhatIf
```

In the following example, the administrator views the outcome of running a command to give a
standard user named JennyL access to event, performance counter, service status, and role and
feature inventory data on a server that is being managed, either locally or remotely, by using
Server Manager. The `WhatIf` parameter is added, meaning that the command actions are not carried
out.

### Example 3

```powershell
Enable-ServerManagerStandardUserRemoting -User JennyL -Confirm
```

In the following example, the administrator gives a standard user named `JennyL` access to event,
performance counter, service status, and role and feature inventory data on a server that is being
managed, either locally or remotely, by using Server Manager. The `Confirm` parameter is added,
meaning that the command prompts for confirmation before performing the action.

## PARAMETERS

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

Specifies the user account name of a standard user who runs Server Manager, and requires access to
event, performance counter, service, and role and feature inventory data for remote servers that are
managed by using the local Server Manager console.

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```
### -WhatIf

Shows what would happen if the cmdlet were run.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WindowsFeature](./Get-WindowsFeature.md)

[Install-WindowsFeature](./Install-WindowsFeature.md)

[Uninstall-WindowsFeature](./Uninstall-WindowsFeature.md)

[Disable-ServerManagerStandardUserRemoting](./Disable-ServerManagerStandardUserRemoting.md)

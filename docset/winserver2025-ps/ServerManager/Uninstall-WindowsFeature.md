---
description: Uninstalls specified Windows Server roles, role services, and features from a computer.
external help file: Microsoft.Windows.ServerManager.PowerShell.dll-Help.xml
Module Name: ServerManager
ms.date: 09/08/2021
online version: https://learn.microsoft.com/powershell/module/servermanager/uninstall-windowsfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-WindowsFeature
---

# Uninstall-WindowsFeature

## SYNOPSIS

Uninstalls specified Windows Server roles, role services, and features from a computer that is
running Windows Server. By adding the Remove parameter, also deletes feature files or payload, from
a computer.

## SYNTAX

### RunningComputer (Default)

```
Uninstall-WindowsFeature [-Name] <Feature[]> [-Restart] [-IncludeManagementTools] [-Remove]
 [-ComputerName <String>] [-Credential <PSCredential>] [-LogPath <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VhdPath

```
Uninstall-WindowsFeature [-Name] <Feature[]> [-Vhd <String>] [-IncludeManagementTools] [-Remove]
 [-ComputerName <String>] [-Credential <PSCredential>] [-LogPath <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Uninstall-WindowsFeature` cmdlet uninstalls and optionally removes specified roles, role
services, and features from a computer that is running Windows Server or from an offline virtual
hard disk (VHD) on which Windows Server is installed. This cmdlet works similarly to the
uninstallation of roles and features in Server Manager with an important exception: by default,
management tools are not uninstalled when you run the `Uninstall-WindowsFeature` cmdlet; you must
add the **IncludeManagementTools** parameter to uninstall associated management tools.

This cmdlet requires elevation; you must be running a Windows PowerShell session as an administrator
to use this cmdlet.

## EXAMPLES

### Example 1

```powershell
Get-WindowsFeature | Where-Object -FilterScript { $_.Installed -Eq $TRUE } | Uninstall-WindowsFeature
```

This example uninstalls any roles or features that are currently installed on the target server.

### Example 2

```powershell
Uninstall-WindowsFeature -Name Web-Server -ComputerName Server1 -Credential contoso\user1
```

This example removes Web Server (IIS) from `Server1`, including all role services. The user account
specified to perform the operation is `contoso\user1`.

### Example 3

```
Get-WindowsFeature | Where-Object -FilterScript { $_.Installed -Eq $FALSE } | Uninstall-WindowsFeature -Remove
```

This example deletes the feature files for any roles or features that currently are not installed on
the local server.

## PARAMETERS

### -ComputerName

Uninstalls and optionally removes one or more roles or features from a specified remote computer.
This parameter accepts only one computer name. If this parameter is not added or no computer name
is specified, the default target is the local computer.

Valid values for the parameter include a NetBIOS name, an IP address, or a fully qualified domain
name of a remote computer that is running Windows Server.

To use an IP address of a remote computer as the value of this parameter, your command must include
the **Credential** parameter. The computer must either be configured for HTTPS transport or the IP
address of the remote computer must be included in the WinRM TrustedHosts list on the local
computer. For information about adding a computer name to the WinRM TrustedHosts list, see "How to
Add a Computer to the Trusted Host List" in
[about_Remote_Troubleshooting](https://go.microsoft.com/fwlink/p/?LinkID=135188).

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies a user account that has access rights to perform this action. If the parameter is not
added or no value is specified, the default value of this parameter is the current user. Enter a
user name in one of the following formats. Quotation marks are optional.

-- "UserName"
-- "Domain\User"
-- "User@Domain.com"
-- A Credential object returned by the [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkID=113311) cmdlet.

If a user name is entered, then a prompt for a password is displayed.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeManagementTools

Specifies the uninstallation of all applicable management tools along with the roles, role services,
or features that are specified in the `Name` parameter. Note that by default, management tools are
not uninstalled when you run the `Uninstall-WindowsFeature` cmdlet; you must add this parameter to
uninstall associated management tools.

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

### -LogPath

Specifies a name and path to a log file. Add this parameter if the results of this cmdlet must be
stored in a log.

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

### -Name

Specifies a list of features to uninstall. This parameter does not support wildcard characters.

```yaml
Type: Feature[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Remove

Deletes feature files for the specified features from the side-by-side store, located at
`%SystemDrive%:\Windows\WinSxS`. If the feature is not yet uninstalled, the command uninstalls the
feature.

When you delete feature files, features that depend upon the files you remove are also deleted. When
you delete feature files for a subfeature, and no other subfeatures for the parent feature are
installed, then files for the entire parent role or feature are deleted.

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

### -Restart

Specifies that the target computer is restarted automatically, if a restart is required by the
uninstallation process for the specified roles or features. This parameter cannot be used with the
**Vhd** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: RunningComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vhd

Specifies the path to an offline VHD. The path can either point to a VHD file or to a location on
which the VHD is already mounted by using Deployment Image Servicing and Management (DISM) tools.

The VHD can be on a local disk on the target computer or on a network shared folder. If the VHD is
in a network shared folder, then the value of this parameter is a UNC path to the VHD. In this case,
the computer account of the computer that you are using to mount the VHD must have read and write
permissions (Read/Write permissions in the File Sharing dialog box or Full Control on the Security
tab of the folder Properties dialog box) on the shared folder or the VHD will not be accessible.
Local loopback UNC paths are not supported. Use either of the following formats for the computer
account: DOMAIN\SERVERNAME$ or SERVERNAME$.

Add the **ComputerName** parameter to specify the target computer you want to use to mount the VHD.
If the **ComputerName** parameter is not specified, then the local computer is used. The computer
that you are using to mount the VHD must be running Windows Server. Any local path, such as
`D:\myFolder`, that is specified by using this parameter is always relative to the target computer.

```yaml
Type: String
Parameter Sets: VhdPath
Aliases:

Required: False
Position: Named
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

### Microsoft.Windows.ServerManager.Commands.Feature[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WindowsFeature](./Get-WindowsFeature.md)

[Install-WindowsFeature](./Install-WindowsFeature.md)

[Enable-ServerManagerStandardUserRemoting](./Enable-ServerManagerStandardUserRemoting.md)

[Disable-ServerManagerStandardUserRemoting](./Disable-ServerManagerStandardUserRemoting.md)

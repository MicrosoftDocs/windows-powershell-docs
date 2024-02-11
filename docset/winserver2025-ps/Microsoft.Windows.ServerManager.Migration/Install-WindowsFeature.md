---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.ServerManager.PowerShell.dll-Help.xml
Module Name: Microsoft.Windows.ServerManager.Migration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.servermanager.migration/install-windowsfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-WindowsFeature
---

# Install-WindowsFeature

## SYNOPSIS
Installs one or more roles, role services, or features on either the local or a specified remote server that is running Windows Server 2012 R2.

## SYNTAX

### ComponentNamesAndRunningComputer (Default)
```
Install-WindowsFeature [-Name] <Feature[]> [-Restart] [-IncludeAllSubFeature] [-IncludeManagementTools]
 [-Source <String[]>] [-ComputerName <String>] [-Credential <PSCredential>] [-LogPath <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ComponentNamesAndVhdPath
```
Install-WindowsFeature [-Name] <Feature[]> -Vhd <String> [-IncludeAllSubFeature] [-IncludeManagementTools]
 [-Source <String[]>] [-ComputerName <String>] [-Credential <PSCredential>] [-LogPath <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ConfigurationFile
```
Install-WindowsFeature -ConfigurationFilePath <String> [-Vhd <String>] [-Restart] [-Source <String[]>]
 [-ComputerName <String>] [-Credential <PSCredential>] [-LogPath <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Install-WindowsFeature** cmdlet installs the specified rrsandf_plural on a computer that is running Windows Server 2012 R2, or on an offline virtual hard disk (VHD) on which Windows Server 2012 R2 is installed.
This cmdlet is equivalent to and replaces the **Add-WindowsFeature** cmdlet, the cmdlet that was used to install roles, role services, and features in Windows Server 2008 R2.This cmdlet works similarly to the arfw in Server Manager, with an important exception:  the cmdlet does not install management tools for rrsandf_plural by default.
To install management tools such as snap-ins on a target server, you must add the *IncludeManagementTools* parameter to your command.

This cmdlet requires elevation; you must be running a Windows PowerShell session as an administrator to use this cmdlet.

## EXAMPLES

### Example 1: Install IIS, including all role services and applicable management tools on the specified computer
```
PS C:\> Install-WindowsFeature -Name "Web-Server" -IncludeAllSubFeature -IncludeManagementTools -ComputerName "Server1" -Credential "contoso.com\PattiFul"
```

This command installs Web Server (IIS), including all role services and applicable management tools, on a computer named Server1, by using the credentials of a user account named contoso.com\PattiFul.

### Example 2: Install all role services and applicable management tools from a configuration file to the default computer
```
PS C:\> Install-WindowsFeature -ConfigurationFilePath "d:\ConfigurationFiles\ADCSConfigFile.xml"
```

This command installs all roles, role services and features that are specified in a configuration file named ADCSConfigFile.xml.
The configuration file was created by clicking Export configuration settings on the Confirm installation selections page of the arfw in Server Manager.

### Example 3: Install AD CS, as specified, from a configuration file to a list of computers
```
PS C:\> $Servers = ('server1', 'server2')
PS C:\> foreach ($Server in $Servers) {Install-WindowsFeature -ConfigurationFilePath D:\ConfigurationFiles\ADCSConfigFile.xml -ComputerName $Server}
```

This command installs Active Directory Certificate Services (AD CS) as specified in a configuration file named ADCSConfigFile.xml.
AD CS is installed on a list of computers that is contained in the variable $Servers.
The configuration file was created by clicking Export configuration settings on the Confirm installation selections page of the arfw in Server Manager.
On the first line, the value of the $Servers variable is set; on the second line, the installation instructions in the ADCSConfigFile.xml configuration file are applied to each of the servers that has been named in $Servers.

### Example 4: Get a list of Windows features using a search string then pipe the results to Install-WindowsFeatures
```
PS C:\> Get-WindowsFeature -Name "Web-*" | Install-WindowsFeature
```

This command retrieves a list of all Windows features beginning with the characters Web, and then pipes the resulting list to **Install-WindowsFeature**.
The result of this cmdlet is all features that start with Web are installed on the local computer.

### Example 5: Install IIS to the local computer specifying a folder that contains the feature files
```
PS C:\> Install-WindowsFeature -Name "Web-Server" -Source "\\server2\winsxs"
```

This command installs Web Server (IIS) on the local computer, specifying that the source of feature files for the installation is a folder, winsxs, on a computer named Server2.
The computer account of the local computer must have Read permissions on the specified share.

## PARAMETERS

### -ComputerName
Specifies a remote computer for which this cmdlet installs one or more available rrsandf_plural.
This parameter accepts only one computer name.
If this parameter is not added, or no computer name is specified, the default target is the local computer.

Valid values for the parameter include a NetBIOS name, an IP address, or a fully qualified domain name of a remote computer that is running Windows Server

To use an IP address of a remote computer as the value of this parameter, your command must include the *Credential* parameter.
The computer must either be configured for HTTPS transport, or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.
For information about adding a computer name to the WinRM TrustedHosts list, see [How to Add a Computer to the Trusted Host List in about_Remote_Troubleshooting](https://go.microsoft.com/fwlink/p/?LinkID=135188).

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

### -ConfigurationFilePath
Specifies a single path to a configuration file which specifies roles and features to be installed, and any configuration parameters needed.
The path can be specified by using a local relative path or by using built-in environment variables prefixed with the `$env` tag (such as $env:systemdrive\filename).
A configuration file can be generated by running the arfw in Server Manager.

If this parameter is specified, then the *Name* parameter cannot be used.

```yaml
Type: String
Parameter Sets: ConfigurationFile
Aliases:

Required: True
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has access rights to perform this action.
If the parameter is not added, or no value is specified, the default value of this parameter is the current user.
Enter a user name in one of the following formats.
Quotation marks are optional.

- UserName
- Domain\User
- User@Domain.com
- A Credential object returned by the Get-Credential cmdlet.

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

### -IncludeAllSubFeature
Indicates that the cmdlet installs all subordinate role services, and all subfeatures of parent roles, role services, or features specified by the *Name* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: ComponentNamesAndRunningComputer, ComponentNamesAndVhdPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeManagementTools
Indicates that the cmdlet installs all applicable management tools of the roles, role services, or features specified by the *Name* parameter.
Although management tools are installed by default when you are installing features by using the arfw, management tools are not installed by default when you install features by using the **Install-WindowsFeature** cmdlet; this parameter must be added to install management tools.

```yaml
Type: SwitchParameter
Parameter Sets: ComponentNamesAndRunningComputer, ComponentNamesAndVhdPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPath
Specifies a name and path to a log file.
Add this parameter if the results of your command must be stored in a log.

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
Specifies a list of features to install.
This parameter does not support wildcard characters.
If this parameter is specified, then the *ConfigurationFilePath* parameter cannot be used.

```yaml
Type: Feature[]
Parameter Sets: ComponentNamesAndRunningComputer, ComponentNamesAndVhdPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Restart
Indicates that cmdlet automatically restarts the target computer if a restart is required by the installation process for the specified roles or features.
This parameter cannot be used with the *Vhd* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: ComponentNamesAndRunningComputer, ConfigurationFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Specifies the path to feature files, if the files are not available in the local feature store of the target computer or VHD.
Valid values for this parameter are either a network path or the path to a Windows image file (WIM).
If you are installing roles or features on an offline VHD, you must use a mounted WIM.
It is not necessary to mount the WIM file for installing on a running physical computer, because a WIM is mounted internally for deployments to a physical computer.
Specify the path by using a local relative path, or by using built-in environment variables that are prefixed with the `$env` tag as shown in the following examples.

The path specified in this parameter is only used if the command cannot find feature files in the local side-by-side store of the specified target computer or VHD.
The command searches for feature files in the following order:

- On the target computer or offline VHD.
- Path specified as the value of this parameter. If you add a Universal Naming Convention (UNC) path, verify that the computer account of the target server has Read permissions on the share. The computer account should be in one of the following formats: DOMAIN\SERVERNAME$ or SERVER$
- Repository path specified by the Group Policy Object (GPO), Specify settings for optional component installation and component repair, located in Computer Configuration/Administrative Templates/System in Local Group Policy Editor. This Group Policy setting controls the following Windows Registry setting: HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Policies\Servicing\LocalSourcePath.
- Windows Update.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vhd
Specifies the path to an offline VHD.
The path can either point to a VHD file, or to a location on which the VHD is already mounted by using Deployment Image Servicing and Management (DISM) tools.

The VHD can be on a local disk on the target computer, or on a network shared folder.
If the VHD is in a network shared folder, then the value of this parameter is a UNC path to the VHD.
In this case, the computer account of the computer that you are using to mount the VHD must have read and write permissions (Read/Write permissions in the File Sharing dialog box, or Full Control on the Security tab of the folder Properties dialog box) on the shared folder, or the VHD will not be accessible.
Local loopback UNC paths are not supported.
Use either of the following formats for the computer account:  DOMAIN\SERVERNAME$ or SERVERNAME$.

Add the *ComputerName* parameter to specify the target computer you want to use to mount the VHD.
If the *ComputerName* parameter is not specified, then the local computer is used.
The computer that you are using to mount the VHD must be running Windows Server 2012 R2.
Any local path, such as D:\myFolder, that is specified by using this parameter is always relative to the target computer.

```yaml
Type: String
Parameter Sets: ComponentNamesAndVhdPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ConfigurationFile
Aliases:

Required: False
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

### System.String[]

### Microsoft.Windows.ServerManager.Commands.Feature[]

## OUTPUTS

### Microsoft.Windows.ServerManager.Commands.FeatureOperationResult

## NOTES

## RELATED LINKS

[Get-WindowsFeature](./Get-WindowsFeature.md)

[Uninstall-WindowsFeature](./Uninstall-WindowsFeature.md)

[Enable-ServerManagerStandardUserRemoting](./Enable-ServerManagerStandardUserRemoting.md)

[Disable-ServerManagerStandardUserRemoting](./Disable-ServerManagerStandardUserRemoting.md)


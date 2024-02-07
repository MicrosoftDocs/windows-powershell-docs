---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/addsdeployment/test-addsforestinstallation?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ADDSForestInstallation
---

# Test-ADDSForestInstallation

## SYNOPSIS
Runs the prerequisites for installing a new forest in Active Directory.

## SYNTAX

```
Test-ADDSForestInstallation -DomainName <String>
 [-SafeModeAdministratorPassword <SecureString>] [-CreateDnsDelegation]
 [-DatabasePath <String>] [-DnsDelegationCredential <PSCredential>] [-NoDnsOnNetwork]
 [-DomainMode <DomainMode>] [-DomainNetbiosName <String>] [-ForestMode <ForestMode>]
 [-InstallDns] [-LogPath <String>] [-NoRebootOnCompletion] [-SkipAutoConfigureDns]
 [-SysvolPath <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

The `Test-ADDSForestInstallation` cmdlet runs those prerequisite checks which would be performed if
you were to use the `Install-ADDSForest` cmdlet to install a new forest in Active Directory. It
differs from using the **WhatIf** parameter with the `Install-ADDSForest` cmdlet in that instead of
summarizing the changes that would occur during the installation process, this cmdlet actually
tests whether those changes are possible given the current environment.

For more information on the scope of these prerequisite checks that the **ADDSDeployment** module
performs when using this cmdlet see the section ADPrep and Prerequisite Checking Architecture in
[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244).

## EXAMPLES

### Example 1: Test the install of a forest to confirm if it is possible

```powershell
Test-ADDSForestInstallation -DomainName "corp.contoso.com" -NoRebootOnCompletion
```

This command runs the prerequisites for installing a new forest named `corp.contoso.com` and
specifies not to reboot after the new forest is created. The user is prompted to provide and
confirm the Directory Services Restore Mode (DSRM) password.

### Example 2: Test the install of a forest to confirm if it is possible

```powershell
$HashArguments = @{
    CreateDNSDelegation = $true
    DatabasePath        = "D:\NTDS"
    DomainMode          = Win2008
    DomainName          = "corp.contoso.com"
    ForestMode          = Win2008R2
    LogPath             = "E:\Logs"
    SysvolPath          = "D:\SYSVOL"
}
Test-ADDSForestInstallation @HashArguments
```

This command runs the prerequisites for installing a new forest that will create a DNS delegation
in the `contoso.com` domain, set the domain functional level to Windows Server 2008 R2 and sets
forest functional level to Windows Server 2008 R2. The command also installs the Active Directory
database and SYSVOL on the `D:` drive, installs the log files on the `E:` drive and has the server
automatically restart after AD DS installation. The user is prompted to provide and confirm the
DSRM password.

## PARAMETERS

### -CreateDnsDelegation

Indicates that the cmdlet creates a DNS delegation that references the new DNS server that you
install along with the domain controller. Valid for Active Directory-integrated DNS only. The
default is computed automatically based on the environment.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabasePath

Specifies the fully qualified, non-Universal Naming Convention (UNC) path to a directory on a fixed
disk of the local computer that contains the domain database, for example, `C:\Windows\NTDS`. The
default is `%SYSTEMROOT%\NTDS`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsDelegationCredential

Specifies the user name and password (account credentials) for creating DNS delegation. The cmdlet
will skip this parameter if the value for the **CreateDnsDelegation** parameter is either specified
or computed to be `$false`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainMode

Specifies the domain functional level of the first domain in the creation of a new forest. Supported
values for this parameter can be either a valid integer or a corresponding enumerated string value.
For instance, to set the domain mode level to Windows Server 2008 R2, you can specify either a value
of `4` or `Win2008R2`.

The acceptable values for this parameter are:

- Windows Server 2003:  2 or Win2003
- Windows Server 2008:  3 or Win2008
- Windows Server 2008 R2:  4 or Win2008R2
- Windows Server 2012:  5 or Win2012
- Windows Server 2012 R2:  6 or Win2012R2

The domain functional level cannot be lower than the forest functional level, but it can be higher.
The default is automatically computed and set.

```yaml
Type: System.DirectoryServices.ActiveDirectory.DomainMode
Parameter Sets: (All)
Aliases: 
Accepted values: Win2008, Win2008R2, Win2012, Win2012R2, WinThreshold, Default

Required: False
Position: Named
Default value: Windows2008R2
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName

Specifies the fully qualified domain name (FQDN) for the root domain in the forest.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainNetbiosName

Specifies the NetBIOS name for the root domain in the new forest. For NetBIOS names to be valid for
use with this parameter they must be single label names of 15 characters or less.

If this parameter is set with a valid NetBIOS name value, then forest installation continues with
the name specified. If this parameter is not set, then the default is automatically computed from
the value of the **DomainName** parameter.

For instance, if this parameter is not specified and a single-label prefix domain name of 15
characters or less is specified within the value of the **DomainName** parameter, then promotion
continues with an automatically generated NetBIOS domain name. For example, the prefix label `corp`
within a full domain name value of `corp.contoso.com` would be a successful name choice.

Note that if the name value given for this parameter is a name of 16 characters or more, then the
forest installation fails.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForestMode

Specifies the forest functional level for the new forest. Supported values for this parameter can be
either a valid integer or a corresponding enumerated string value. For example, to set the forest
mode level to Windows Server 2008 R2, you can specify either a value of `4` or `Win2008R2`.

The acceptable values for this parameter are:

- Windows Server 2003:  2 or Win2003
- Windows Server 2008:  3 or Win2008
- Windows Server 2008 R2:  4 or Win2008R2
- Windows Server 2012:  `5` or `Win2012`
- Windows Server 2012 R2:  `6` or `Win2012R2`

The default forest functional level in Windows Server is typically the same as the version you are
running. However, the default forest functional level in Windows Server 2008 R2 when you create a
new forest is Windows Server 2003 or `2`.

```yaml
Type: System.DirectoryServices.ActiveDirectory.ForestMode
Parameter Sets: (All)
Aliases: 
Accepted values: Win2008, Win2008R2, Win2012, Win2012R2, WinThreshold, Default

Required: False
Position: Named
Default value: Windows2008R2
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallDns

Indicates that the cmdlet installs and configures the DNS Server service for the new forest. For
forest installation, the default is `$true`.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPath

Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer
where the log file for this operation is written. For instance, `C:\Logs`. The default log file path
if no other path is specified with this parameter is `%SYSTEMROOT%\NTDS`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoDnsOnNetwork

Indicates that the DNS service is not available on the network. This parameter is used only when the
IP setting of the network adapter for this computer is not configured with the name of a DNS server
for name resolution. It indicates that a DNS server is installed on this computer for name
resolution. Otherwise, the IP settings of the network adapter must first be configured with the
address of a DNS server.

Omitting this parameter indicates that the TCP/IP client settings of the network adapter on this
server computer is used to contact a DNS server. Therefore, if you are not specifying this
parameter, ensure that TCP/IP client settings are first configured with a preferred DNS server
address.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRebootOnCompletion

Indicates that the cmdlet does not reboot the computer upon completion of the command.

Omitting this parameter indicates the computer is rebooted upon completion of the command,
regardless of success or failure. As a general rule, Microsoft support recommends that you not use
this parameter except for testing or troubleshooting purposes because once configuration has
completed the server will not function correctly as either a member server or a DC until it is
rebooted.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SafeModeAdministratorPassword

Specifies the password for the administrator account when the computer is started in Safe Mode or a
variant of Safe Mode, such as Directory Services Restore Mode. You must supply a password that meets
the password complexity rules of the domain and the password cannot be blank. If specified with a
value, the value must be a secure string.

If this parameter is not specified, the cmdlet prompts you to enter and confirm a masked password.
This is the preferred usage when running the cmdlet interactively. If there are no other arguments
specified with the cmdlet, you are prompted to enter a masked password for this parameter but no
confirmation of the password entered is made. This is not recommended as it could allow a mistyped
password to be configured. Another available advanced option is to use the
`ConvertTo-SecureString` cmdlet and specify the password string inline as unmasked console input,
which is also not a recommended security best practice in production deployments.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAutoConfigureDns

Indicates that the cmdlet skips automatic configuration of DNS client settings, forwarders, and root
hints. This parameter is in effect only if the DNS Server service is already installed.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -SysvolPath

Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer
where the Sysvol file is written. For example, `C:\Logs\SYSVOL`. The default path if no other path
is specified with this parameter is `%SYSTEMROOT%\SYSVOL`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244)

[Install-ADDSForest](./Install-ADDSForest.md)

[Test-ADDSDomainInstallation](./Test-ADDSDomainInstallation.md)

[Test-ADDSDomainControllerInstallation](./Test-ADDSDomainControllerInstallation.md)

[Install-ADDSDomainController](./Install-ADDSDomainController.md)

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkId=113291)

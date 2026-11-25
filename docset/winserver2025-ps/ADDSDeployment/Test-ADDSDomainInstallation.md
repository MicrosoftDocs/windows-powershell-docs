---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/addsdeployment/test-addsdomaininstallation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ADDSDomainInstallation
---

# Test-ADDSDomainInstallation

## SYNOPSIS
Runs the prerequisites for installing a new Active Directory domain configuration.

## SYNTAX

```
Test-ADDSDomainInstallation -NewDomainName <String> -ParentDomainName <String>
 [-SafeModeAdministratorPassword <SecureString>] [-ADPrepCredential <PSCredential>]
 [-AllowDomainReinstall] [-CreateDnsDelegation] [-Credential <PSCredential>]
 [-DatabasePath <String>] [-DnsDelegationCredential <PSCredential>] [-NoDnsOnNetwork]
 [-DomainMode <DomainMode>] [-DomainType <DomainType>] [-NoGlobalCatalog] [-InstallDns]
 [-LogPath <String>] [-NewDomainNetbiosName <String>] [-NoRebootOnCompletion]
 [-ReplicationSourceDC <String>] [-SiteName <String>] [-SkipAutoConfigureDns]
 [-SysvolPath <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

The `Test-ADDSDomainInstallation` cmdlet runs those prerequisite checks which would be performed if
you were to use the `Install-ADDSDomainController` cmdlet to install a new Active Directory domain
configuration. It differs from using the **WhatIf** parameter with the
`Install-ADDSDomainController` cmdlet in that instead of summarizing the changes that would occur
during the installation process, this cmdlet actually tests whether those changes are possible
given the current environment.

For more information on the scope of these prerequisite checks that the **ADDSDeployment** module
performs when using this cmdlet see the section ADPrep and Prerequisite Checking Architecture in
[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244).

## EXAMPLES

### Example 1: Test if installing a child domain is possible

```powershell
@HashArguments = {
    CreateDNSDelegation  = $true
    Credential           = (Get-Credential CORP\EnterpriseAdmin1)
    DatabasePath         = "D:\NTDS"
    DomainMode           = Win2003
    InstallDNS           = $true
    NewDomainName        = "child"
    NoRebootOnCompletion = $true
    ParentDomainName     = "corp.contoso.com"
    ReplicationSourceDC  = "DC1.corp.contoso.com"
    LogPath              = "E:\Logs"
    SiteName             = "Houston"
    SYSVOLPath           = "D:\SYSVOL"
}
Test-ADDSDomainInstallation @HashArguments
```

This command runs the prerequisites to determine if installing a new child domain named
`child.corp.contoso.com` using credentials of `CORP\EnterpriseAdmin1` is possible. This command
also installs a DNS server, creates a DNS delegation in the `corp.contoso.com` domain, sets the
domain functional level to Windows Server 2003, makes the domain controller a global catalog server
in a site named `Houston`, and uses `DC1.corp.contoso.com` as the replication source domain
controller. The command also installs the Active Directory database and SYSVOL on the `D:\` drive,
installs the log files on the `E:\` drive, has the server not automatically restart after the
domain installation is complete and prompts the user to provide and confirm the Directory Services
Restore Mode (DSRM) password to complete and commit the installation of the domain in Active
Directory.

## PARAMETERS

### -ADPrepCredential

Specifies the user name and password that corresponds to the account to be used for running
operations, if required, to prepare Active Directory prior to the installation of this domain. Use
the `Get-Credential` cmdlet to prompt the user to supply a password.

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

### -AllowDomainReinstall

Indicates that the cmdlet recreates an existing domain is to be recreated.

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

### -CreateDnsDelegation

Indicates whether to create a DNS delegation that references the new DNS server that you are
installing along with the domain controller. Valid for Active Directory-integrated DNS only. The
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

### -Credential

Specifies the user name and password that corresponds to the account used to install the domain
controller. Use the `Get-Credential` cmdlet to prompt the user to supply a password.

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

Specifies the user name and password for the user that creates the DNS delegation. This parameter
is skipped if the value for the **CreateDnsDelegation** parameter is either specified or computed
to be `$false`.

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

Specifies the domain functional level of the first domain in the creation of a new forest.
Supported values for this parameter can be either a valid integer or a corresponding enumerated
string value. For instance, to set the domain mode level to Windows Server 2008 R2, you can specify
either a value of `4` or `Win2008R2`.

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

### -DomainType

Specifies the type of domain that this cmdlet creates: a new domain tree in an existing forest
(supported values are `TreeDomain` or `tree`), a child of an existing domain (supported values are
`ChildDomain` or `child`). The default is `ChildDomain`.

```yaml
Type: DomainType
Parameter Sets: (All)
Aliases:
Accepted values: ChildDomain, TreeDomain

Required: False
Position: Named
Default value: ChildDomain
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

### -InstallDns

Indicates that this cmdlet installs and configures the DNS Server service for the domain or domain
tree. For domain installation, if this parameter is left unspecified and the parent domain (or in
the case of a domain tree, the forest root domain) already hosts and stores the DNS names for the
domain, then the default for this parameter is `$true` and the DNS server is installed. Otherwise,
if DNS domain names are hosted outside of Active Directory, the default is `$false` and no DNS
server is installed.

To test if DNS domain names are hosted outside of Active Directory, this cmdlet uses a start of
authority (SOA) type DNS. For instance, if the value of **NewDomainName** is `corp.contoso.com`,
Active Directory performs an SOA query for `corp.contoso.com` and ensures that the zone name in the
response is `corp.contoso.com`.

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
that will contain the domain log files, for example, `C:\Windows\Logs`. The default is
`%SYSTEMROOT%\NTDS`.

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

### -NewDomainName

Specifies the new name of the domain. If the value set for **DomainType** is set to `TreeDomain`,
this parameter can be used to specify the fully qualified domain name (FQDN) for the new domain
tree (for example, `contoso.com`). If the value set for **DomainType** is set to `ChildDomain`,
this parameter can be used to specify a single label domain name for the child domain (for example,
specify corp to make a new domain `corp.contoso.com` if the new domain is in the `contoso.com`
domain tree).

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

### -NewDomainNetbiosName

Specifies the NetBIOS name for the new domain. For NetBIOS names to be valid for use with this
parameter they must be single label names of 15 characters or less.

If this parameter is set with a valid NetBIOS name value, then promotion continues with the name
specified. If this parameter is not set, then the default is automatically computed from the value
of the **NewDomainName** parameter.

For instance, if this parameter is not specified and a single-label prefix domain name of 15
characters or less is specified within the value of the **NewDomainName** parameter, then promotion
continues with an automatically generated NetBIOS domain name. For example, the prefix label corp
within a full domain name value of `corp.contoso.com` would be a successful name choice. If the
label is more than 16 characters, the operation will fail.

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

Omitting this parameter, the default value, indicates that the TCP/IP client settings of the network
adapter on this server computer is used to contact a DNS server. Therefore, if you are not
specifying this parameter, ensure that TCP/IP client settings are first configured with a preferred
DNS server address.

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

### -NoGlobalCatalog

Indicates that the read-only domain controller (RODC) will not be a global catalog server. By
default, the domain controller that you are installing is a global catalog server.

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

Indicates that the cmdlet restarts the computer upon completion, regardless of success. By default,
reboot upon completion occurs when this cmdlet is used and this parameter is omitted. As a general
rule, Microsoft support recommends that you not use this parameter except for testing or
troubleshooting purposes because once configuration has completed the server will not function
correctly as either a member server or a DC until it is rebooted.

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

### -ParentDomainName

Specifies the fully qualified domain name (FQDN) of an existing parent domain.

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

### -ReplicationSourceDC

Specifies the fully qualified domain name (FQDN) of the domain controller to be used as the source
for replicating to this domain. The default value for this parameter is automatically computed from
the environment.

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

### -SafeModeAdministratorPassword

Supplies the password for the administrator account when the computer is started in Safe Mode or a
variant of Safe Mode, such as Directory Services Restore Mode. You must supply a password that meets
the password complexity rules of the domain and the password cannot be blank. If specified with a
value, the value must be a secure string.

If this parameter is not specified, the cmdlet prompts you to enter and confirm a masked password.
This is the preferred usage when running the cmdlet interactively. If additionally there are no
other arguments specified with the cmdlet, you are prompted to enter a masked password for this
parameter but no confirmation of the password entered is made. This is not recommended as it could
allow a mistyped password to be configured. Another available advanced option is to use the
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

### -SiteName

Specifies the name of an existing site where you can place the new domain controller. The default
value is the site that is associated with the subnet that includes the IP address of this server. If
no such site exists, the default is the site of the replication source domain controller.

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

### -SkipAutoConfigureDns

Indicates that this cmdlet skips automatic configuration of DNS client settings, forwarders, and
root hints. This parameter is in effect only if the DNS Server service is already installed.

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

Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer,
for example, `C:\Windows\SYSVOL`. The default is `%SYSTEMROOT%\SYSVOL`.

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

[Install-ADDSDomain](./Install-ADDSDomain.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkId=113291)

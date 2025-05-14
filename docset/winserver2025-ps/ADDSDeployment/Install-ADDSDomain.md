---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/addsdeployment/install-addsdomain?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-ADDSDomain
---

# Install-ADDSDomain

## SYNOPSIS

Creates a new domain in an existing Active Directory forest.

## SYNTAX

```
Install-ADDSDomain [-SkipPreChecks] -NewDomainName <String> -ParentDomainName <String>
[-SafeModeAdministratorPassword <SecureString>] [-ADPrepCredential <PSCredential>]
[-AllowDomainReinstall] [-CreateDnsDelegation] [-Credential <PSCredential>]
[-DatabasePath <String>] [-DnsDelegationCredential <PSCredential>] [-NoDnsOnNetwork]
[-DomainMode <DomainMode>] [-DomainType <DomainType>] [-NoGlobalCatalog] [-InstallDns]
[-LogPath <String>] [-NewDomainNetbiosName <String>] [-NoRebootOnCompletion]
[-ReplicationSourceDC <String>] [-SiteName <String>] [-SkipAutoConfigureDns]
[-SysvolPath <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Install-ADDSDomain` cmdlet installs an Active Directory domain configuration.

## EXAMPLES

### Example 1: Install a new child domain

```powershell
$params = @{
    Credential = (Get-Credential CORP\EnterpriseAdmin1)
    NewDomainName = "child"
    ParentDomainName = "corp.contoso.com"
    InstallDNS = $true
    CreateDNSDelegation = $true
    DomainMode = "Win2003"
    ReplicationSourceDC = "DC1.corp.contoso.com"
    SiteName = "Houston"
    DatabasePath = "D:\NTDS"
    SYSVOLPath = "D:\SYSVOL"
    LogPath = "E:\Logs"
    NoRebootOnCompletion = $true
}
Install-ADDSDomain @HashArguments
```

This command installs a new child domain named `child.corp.contoso.com` using credentials of
`CORP\EnterpriseAdmin1`. This command also installs a DNS server, creates a DNS delegation in the
`corp.contoso.com` domain, sets the domain functional level to Windows Server 2003, makes the
domain controller a global catalog server in a site named Houston, uses `DC1.corp.contoso.com` as
the replication source domain controller, installs the Active Directory database and SYSVOL on the
`D:\` drive. Additionally this command also installs the log files on the `E:\` drive, has the
server not automatically restart after the domain installation is complete and causes the user to
be prompted to provide and confirm the Directory Services Restore Mode (DSRM) password to complete
and commit the installation of the domain in Active Directory.

## PARAMETERS

### -ADPrepCredential

Specifies the user name and password that corresponds to the account to be used for running
operations to prepare Active Directory prior to the installation of this domain. Use the
`Get-Credential` cmdlet to prompt the user to supply a password.

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

Indicates that the cmdlet recreates an existing domain.

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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
disk of the local computer that contains the domain database, for instance, `C:\Windows\NTDS`. The
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

Specifies the user name and password (account credentials) for creating the DNS delegation. This
parameter is skipped if the value for the **CreateDnsDelegation** parameter is either specified or
computed to be `$false`.

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
- Windows Server 2016: 7 or Windows2016Domain

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

Specifies the type of domain that this cmdlet creates. You can create a new domain tree in an
existing forest (supported values are `TreeDomain` or `tree`) or a child of an existing domain
(supported values are `ChildDomain` or `child`). The default is `ChildDomain`.

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

Indicates that the cmdlet installs and configures the DNS Server service for the domain or domain
tree. For domain installation, if this parameter is left unspecified and the parent domain (or in
the case of a domain tree, the forest root domain) already hosts and stores the DNS names for the
domain, then the default for this parameter is `$true` and the DNS server is installed. Otherwise,
if DNS domain names are hosted outside of Active Directory, the default is `$false` and no DNS
server is installed.

To test if DNS domain names are hosted outside of Active Directory, this cmdlet uses a start of
authority (SOA) type DNS query. For instance, if the value of **NewDomainName** parameter is
`corp.contoso.com`, Active Directory performs an SOA query for `corp.contoso.com` and ensures that
the zone name in the response is `corp.contoso.com`.

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
that contains the domain log files, for instance, `C:\Windows\Logs`. The default is
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

Specifies the new domain name that this cmdlet installs. If the value set for the **DomainType**
parameter is set to `TreeDomain`, this parameter can be used to specify the fully qualified domain
name (FQDN) for the new domain tree. If the value for the **DomainType** parameter is set to
`ChildDomain`, this parameter can be used to specify a single label domain name for the child
domain.

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
continues with an automatically generated NetBIOS domain name. For example, the prefix label `corp`
within a full domain name value of `corp.contoso.com` would be a successful name choice.

Note that if the name value given for this parameter is a name of 16 characters or more, then the
domain installation will fail.

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

Omitting this parameter (the default) indicates that the TCP/IP client settings of the network
adapter on this server computer is used to contact a DNS server. Therefore, if you do not specify
this parameter, ensure that TCP/IP client settings are first configured with a preferred DNS server
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

### -NoGlobalCatalog

Specifies that the read-only domain controller (RODC) will not be a global catalog server.
By default, the domain controller that you are installing is a global catalog server.

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

Indicates that the cmdlet does not reboot the computer upon completion. By default, reboot upon
completion occurs when this cmdlet is used and this parameter is omitted. As a general rule,
Microsoft support recommends that you not use this parameter except for testing or troubleshooting
purposes because once configuration has completed the server will not function correctly as either a
member server or a DC until it is rebooted.

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

### -SkipPreChecks

Indicates that the cmdlet performs only a base set of validations. This behavior is equivalent to
the validations that were performed when using `Dcpromo.exe` in earlier versions of Windows Server
to add a new domain. When this switch parameter is set, it specifies that additional preliminary
checks should be bypassed. For more information on the scope of these additional preliminary checks
that the **ADDSDeployment** module performs by default when using Windows Server 2012, refer to the
table in the section ADPrep and Prerequisite Checking Architecture in
[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244).

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

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

- When a new domain tree is created in an existing forest, a two-way, transitive tree root trust is
  established by default.

## RELATED LINKS

[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244)

[Install-ADDSDomainController](./Install-ADDSDomainController.md)

[Install-ADDSForest](./Install-ADDSForest.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkId=113291)

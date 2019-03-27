---
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
ms.assetid: CA3E100C-A668-4B7F-9080-43D66DBC5BC6
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Install-ADDSDomain

## SYNOPSIS
Installs a new Active Directory domain configuration.

## SYNTAX

```
Install-ADDSDomain [-SkipPreChecks] -NewDomainName <String> -ParentDomainName <String>
 [-SafeModeAdministratorPassword <SecureString>] [-ADPrepCredential <PSCredential>] [-AllowDomainReinstall]
 [-CreateDnsDelegation] [-Credential <PSCredential>] [-DatabasePath <String>]
 [-DnsDelegationCredential <PSCredential>] [-NoDnsOnNetwork] [-DomainMode <DomainMode>]
 [-DomainType <DomainType>] [-NoGlobalCatalog] [-InstallDns] [-LogPath <String>]
 [-NewDomainNetbiosName <String>] [-NoRebootOnCompletion] [-ReplicationSourceDC <String>] [-SiteName <String>]
 [-SkipAutoConfigureDns] [-SysvolPath <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Install-ADDSDomain cmdlet installs a new Active Directory domain configuration.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Install-ADDSDomain -Credential (Get-Credential CORP\EnterpriseAdmin1) -NewDomainName child -ParentDomainName corp.contoso.com -InstallDNS -CreateDNSDelegation -DomainMode Win2003 -ReplicationSourceDC DC1.corp.contoso.com -SiteName Houston -DatabasePath "D:\NTDS" -SYSVOLPath "D:\SYSVOL" -LogPath "E:\Logs" -NoRebootOnCompletion
```

Description

-----------

Installs a new child domain named child.corp.contoso.com using credentials of CORP\EnterpriseAdmin1.
This example also installs a DNS server, creates a DNS delegation in the corp.contoso.com domain, sets the domain functional level to Windows Server 2003, makes the domain controller a global catalog server in a site named Houston, uses DC1.corp.contoso.com as the replication source domain controller, installs the Active Directory database and SYSVOL on the D:\ drive, installs the log files on the E:\ drive, has the server not automatically restart after the domain installation is complete and causes the user to be prompted to provide and confirm the Directory Services Restore Mode (DSRM) password to complete and commit the installation of the domain in Active Directory.

## PARAMETERS

### -ADPrepCredential
Specifies the user name and password that corresponds to the account to be used for running operations (if they are required) to prepare Active Directory prior to the installation of this domain.
Specify "`(Get-Credential)`" to prompt the user to supply a password.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowDomainReinstall
If this parameter is included, it specifies that an existing domain is to be recreated.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateDnsDelegation
Indicates whether to create a DNS delegation that references the new DNS server that you are installing along with the domain controller.
Valid for Active Directory-integrated DNS only.
The default is computed automatically based on the environment.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user name and password that corresponds to the account used to install the domain controller.
Specify "`(Get-Credential)`" to prompt the user to supply a password.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabasePath
Specifies the fully qualified, non-Universal Naming Convention (UNC) path to a directory on a fixed disk of the local computer that contains the domain database, for example, C:\Windows\NTDS.
The default is %SYSTEMROOT%\NTDS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsDelegationCredential
Specifies the user name and password (account credentials) for the user creating DNS delegation.
This parameter is skipped if the value for the **-CreateDnsDelegation** parameter is either specified or computed to be $false.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainMode
Specifies the domain functional level during creation of a new domain.
Supported values for this parameter can be either a valid integer or a corresponding enumerated string value.
For example, to set the domain mode level to Windows Server 2008 R2, you can specify either a value of 4 or "Win2008R2".
Other supported values include those for Windows Server 2003 (2, Win2003) Windows Server 2008 (3, Win2008) and Windows Server 2012 (5, Win8).
The domain functional level cannot be lower than the forest functional level, but it can be higher.
The default is Windows Server 2012 (5, Win8).

```yaml
Type: DomainMode
Parameter Sets: (All)
Aliases: 
Accepted values: Win2003, Win2008, Win2008R2, Win2012, Default

Required: False
Position: Named
Default value: Windows2008R2
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainType
Indicates the type of domain that you want to create: a new domain tree in an existing forest (supported values are "TreeDomain" or "tree"), a child of an existing domain (supported values are "ChildDomain" or "child").
The default is ChildDomain.

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
When this parameter is specified any warnings that might normally appear during the installation of the domain will be suppressed to allow the cmdlet to complete its operation.
This parameter can be useful to include when scripting installation.

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

### -InstallDns
Specifies whether the DNS Server service should be installed and configured for the domain or domain tree.
For domain installation, if this parameter is left unspecified and the parent domain (or in the case of a domain tree, the forest root domain) already hosts and stores the DNS names for the domain, then the default for this parameter is $true and the DNS server will be installed.
Otherwise, if DNS domain names are hosted outside of Active Directory, the default is $false and no DNS server will be installed.

To test if DNS domain names are hosted outside of Active Directory, this cmdlet uses a start of authority (SOA) type DNS query to ask the question "Does a zone exist for the domain name?" For example, if the value of **-NewDomainName** is "corp.contoso.com", Active Directory performs an SOA query for "corp.contoso.com" and ensures that the zone name in the response is " corp.contoso.com".

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPath
Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer that contains the domain log files, for example, C:\Windows\Logs.
The default is %SYSTEMROOT%\NTDS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDomainName
If the value set for **-DomainType** is set to "TreeDomain", this parameter can be used to specify the fully qualified domain name (FQDN) for the new domain tree (for example, "contoso.com").
If the value set for **-DomainType** is set to "ChildDomain", this parameter can be used to specify a single label domain name for the child domain (for example, specify "corp" to make a new domain "corp.contoso.com" if the new domain is in the contoso.com domain tree).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDomainNetbiosName
Specifies the NetBIOS name for the new domain.
For NetBIOS names to be valid for use with this parameter they must be single label names of 15 characters or less.

If this parameter is set with a valid NetBIOS name value, then promotion continues with the name specified.
If this parameter is not set, then the default is automatically computed from the value of the **-NewDomainName** parameter.

For example, if this parameter is not specified and a single-label prefix domain name of 15 characters or less is specified within the value of the **-NewDomainName** parameter, then promotion continues with an automatically generated NetBIOS domain name.
For example, the prefix label "corp" within a full domain name value of "corp.contoso.com" would be a successful name choice.

Note that if the name value given for this parameter (or if it is omitted, the value of the single-label prefix domain name within the **-NewDomainName** parameter) is a name of 16 characters or more, then the domain installation fails.
For example, if a value of "CORPORATEHEADQTRS" were specified for this parameter (or if this parameter is omitted and the value of **-NewDomainName** were set to be "corporateheadqtrs.contoso.com") then the domain installation will fail.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoDnsOnNetwork
Specifies that DNS service is not available on the network.
This parameter is used only when the IP setting of the network adapter for this computer is not configured with the name of a DNS server for name resolution.
It indicates that a DNS server will be installed on this computer for name resolution.
Otherwise, the IP settings of the network adapter must first be configured with the address of a DNS server.

Omitting this parameter (the default) indicates that the TCP/IP client settings of the network adapter on this server computer will be used to contact a DNS server.
Therefore, if you are not specifying this parameter, ensure that TCP/IP client settings are first configured with a preferred DNS server address.

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

### -NoGlobalCatalog
Specifies that the read-only domain controller (RODC) will not be a global catalog server.
By default, the domain controller that you are installing is a global catalog server.

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

### -NoRebootOnCompletion
Specifies whether to restart the computer upon completion, regardless of success.
(By default, reboot upon completion occurs when this cmdlet is used and this parameter is omitted.) As a general rule, Microsoft support recommends that you not use this parameter except for testing or troubleshooting purposes because once configuration has completed the server will not function correctly as either a member server or a DC until it is rebooted.

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

### -ParentDomainName
Specifies the fully qualified domain name (FQDN) of an existing parent domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationSourceDC
Specifies the fully qualified domain name (FQDN) of the domain controller to be used as the source for replicating to this domain.
The default value for this parameter is automatically computed from the environment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -SafeModeAdministratorPassword
Supplies the password for the administrator account when the computer is started in Safe Mode or a variant of Safe Mode, such as Directory Services Restore Mode.
You must supply a password that meets the password complexity rules of the domain and the password cannot be blank.
If specified with a value, the value must be a secure string.

If this parameter is not specified, the cmdlet prompts you to enter and confirm a masked password.
This is the preferred usage when running the cmdlet interactively.
If additionally there are no other arguments specified with the cmdlet, you will be prompted to enter a masked password for this parameter but no confirmation of the password entered will be made (which is not recommended as it could allow a mistyped password to be configured).
Another available advanced option is to use the **ConvertTo-SecureString** cmdlet and specify the password string inline as unmasked console input, which is also not a recommended security best practice in production deployments.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteName
Specifies the name of an existing site where you can place the new domain controller.
The default value is the site that is associated with the subnet that includes the IP address of this server.
If no such site exists, the default is the site of the replication source domain controller.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAutoConfigureDns
Skips automatic configuration of DNS client settings, forwarders, and root hints.
This parameter is in effect only if the DNS Server service is already installed.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipPreChecks
Specifies that only a base set of validations will be performed.
This behavior is equivalent to the validations that were performed when using Dcpromo.exe in earlier versions of Windows Server to add a new domain.
When this switch parameter is set, it specifies that additional preliminary checks should be bypassed.
For more information on the scope of these additional preliminary checks that the ADDSDeployment module performs by default when using Windows Server 2012, refer to the table in the section "Prerequisite Checking" in the Understand and Troubleshoot AD DS Simplified Administration in Windows Server 2012 guide (http://go.microsoft.com/fwlink/?LinkID=237244).

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

### -SysvolPath
Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer, for example, C:\Windows\SYSVOL.
The default is %SYSTEMROOT%\SYSVOL.

```yaml
Type: String
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* When a new domain tree is created in an existing forest, a two-way, transitive tree root trust is established by default.

## RELATED LINKS

[Install-ADDSDomainController](./Install-ADDSDomainController.md)

[Install-ADDSForest](./Install-ADDSForest.md)

[Install-ADDS-Domain](00000000-0000-0000-0000-000000000000)


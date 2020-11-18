---
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
online version: 
schema: 2.0.0
title: Test-ADDSForestInstallation
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4BAB511B-0000-4AC1-8258-F945353FA10E
---

# Test-ADDSForestInstallation

## SYNOPSIS
Runs the prerequisites (only) for installing a new forest in Active Directory.

## SYNTAX

```
Test-ADDSForestInstallation -DomainName <String> [-SafeModeAdministratorPassword <SecureString>]
 [-CreateDnsDelegation] [-DatabasePath <String>] [-DnsDelegationCredential <PSCredential>] [-NoDnsOnNetwork]
 [-DomainMode <DomainMode>] [-DomainNetbiosName <String>] [-ForestMode <ForestMode>] [-InstallDns]
 [-LogPath <String>] [-NoRebootOnCompletion] [-SkipAutoConfigureDns] [-SysvolPath <String>] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The Test-ADDSForestInstallation cmdlet runs those prerequisite checks (only) which would be performed if you were to use the Install-ADDSForest cmdlet to install a new forest in Active Directory.
It differs from using the **-WhatIf** parameter with the Install-ADDSForest cmdlet in that instead of summarizing the changes that would occur during the installation process, this cmdlet actually tests whether those changes are possible given the current environment.

For more information on the scope of these prerequisite checks that the ADDSDeployment module performs when using this cmdlet see the section "Prerequisite Checking" in Understand and Troubleshoot AD DS Simplified Administrationhttp://go.microsoft.com/fwlink/?LinkID=237244.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Test-ADDSForestInstallation -DomainName "corp.contoso.com" -NoRebootOnCompletion
```

Description

-----------

Runs the prerequisites (only) for installing a new forest named corp.contoso.com that causes the user to be prompted to provide and confirm the Directory Services Restore Mode (DSRM) password and specifies not to reboot after the new forest is created.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Test-ADDSForestInstallation -DomainName corp.contoso.com -CreateDNSDelegation -DomainMode Win2008 -ForestMode Win2008R2 -DatabasePath "D:\NTDS" -SysvolPath "D:\SYSVOL" -LogPath "E:\Logs"
```

Description

-----------

Runs the prerequisites (only) for installing a new forest that will create a DNS delegation in the contoso.com domain, set the domain functional level to Windows Server 2008 R2 and sets forest functional level to Windows Server 2008 R2, install the Active Directory database and SYSVOL on the D:\ drive, install the log files on the E:\ drive and has the server automatically restart after AD DS installation is complete and prompts the user to provide and confirm the Directory Services Restore Mode (DSRM) password.

## PARAMETERS

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
Specifies the user name and password (account credentials) for creating DNS delegation.
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
Specifies the domain functional level of the first domain in the creation of a new forest.
Supported values for this parameter can be either a valid integer or a corresponding enumerated string value.
For example, to set the domain mode level to Windows Server 2008 R2, you can specify either a value of 4 or "Win2008R2".
Other supported values include:

-- Windows Server 2003 (2, Win2003) 

   -- Windows Server 2008 (3, Win2008) 

   -- Windows Server 2008 R2 (4, Win2008R2) 

   -- Windows Server 2012 (5, Win2012) 

   -- Windows Server 2012 R2 (6, Win2012R2)

The domain functional level cannot be lower than the forest functional level, but it can be higher.
The default is automatically computed and set.

```yaml
Type: DomainMode
Parameter Sets: (All)
Aliases: 
Accepted values: Win2008, Win2008R2, Win2012, Win2012R2, Default

Required: False
Position: Named
Default value: Windows2008R2
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the fully qualified domain name (FQDN) for the root (first) domain in the forest.

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

### -DomainNetbiosName
Specifies the NetBIOS name for the root domain in the new forest.
For NetBIOS names to be valid for use with this parameter they must be single label names of 15 characters or less.

If this parameter is set with a valid NetBIOS name value, then forest installation continues with the name specified.
If this parameter is not set, then the default is automatically computed from the value of the **-DomainName** parameter.

For example, if this parameter is not specified and a single-label prefix domain name of 15 characters or less is specified within the value of the **-DomainName** parameter, then promotion continues with an automatically generated NetBIOS domain name.
For example, the prefix label "corp" within a full domain name value of "corp.contoso.com" would be a successful name choice.

Note that if the name value given for this parameter (or if it is omitted, the value of the single-label prefix domain name within the **-DomainName** parameter) is a name of 16 characters or more, then the forest installation fails.
For example, if a value of "CORPORATEHEADQTRS" were specified for this parameter (or if this parameter is omitted and the value of **-DomainName** were set to be "corporateheadqtrs.contoso.com") then the forest installation will fail.

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

### -Force
When this parameter is specified any warnings that might normally appear during the installation of the new forest will be suppressed to allow the cmdlet to complete its operation.
This parameter can be useful to include when scripting installation of new forests.

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

### -ForestMode
Specifies the forest functional level for the new forest.
Supported values for this parameter can be either a valid integer or a corresponding enumerated string value.
For example, to set the forest mode level to Windows Server 2008 R2, you can specify either a value of 4 or "Win2008R2".
The supported values include:

-- Windows Server 2003 (2, Win2003) 

   -- Windows Server 2008 (3, Win2008) 

   -- Windows Server 2008 R2 (4, Win2008R2) 

   -- Windows Server 2012 (5, Win2012) 

   -- Windows Server 2012 R2 (6, Win2012R2)

The default forest functional level in Windows Server when you create a new forest is based on the version you are running. 
However, the default forest functional level in Windows Server 2008 R2 when you create a new forest is Windows Server 2003 (2).

```yaml
Type: ForestMode
Parameter Sets: (All)
Aliases: 
Accepted values: Win2008, Win2008R2, Win2012, Win2012R2, Default

Required: False
Position: Named
Default value: Windows2008R2
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallDns
Specifies whether the DNS Server service should be installed and configured for the new forest.
For forest installation, the default is $true (a new DNS server will be installed and configured).

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
Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer where the log file for this operation will be written.
For example, C:\Logs.
The default log file path if no other path is specified with this parameter is %SYSTEMROOT%\NTDS.

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

### -NoRebootOnCompletion
Specifying this parameter indicates that the computer should not be rebooted upon completion of the command.
Omitting this parameter (the default) indicates the computer will be rebooted upon completion of the command, regardless of success or failure.
As a general rule, Microsoft support recommends that you not use this parameter except for testing or troubleshooting purposes because once configuration has completed the server will not function correctly as either a member server or a DC until it is rebooted.

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

### -SysvolPath
Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer where the Sysvol file will be written.
For example, C:\Logs\SYSVOL.
The default path if no other path is specified with this parameter is %SYSTEMROOT%\SYSVOL.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Install-ADDSForest](./Install-ADDSForest.md)

[Test-ADDSDomainInstallation](./Test-ADDSDomainInstallation.md)

[Test-ADDSDomainControllerInstallation](./Test-ADDSDomainControllerInstallation.md)


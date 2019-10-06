---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsServer-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsServer
ms.assetid: 6DEAAEEF-E52C-49D7-9FBB-8C7E996D4E9B
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Test-HgsServer
ms.reviewer:
---

# Test-HgsServer

## SYNOPSIS
Tests if the local computer can function as a Host Guardian Service server node.

## SYNTAX

### PrimaryServer_HgsDomain (Default)
```
Test-HgsServer [[-HgsDomainName] <String>] [-SafeModeAdministratorPassword <SecureString>]
 [-LogDirectory <String>] [-DatabasePath <String>] [<CommonParameters>]
```

### AdditionalServer
```
Test-HgsServer [[-HgsDomainName] <String>] [-HgsDomainCredential] <PSCredential> [-HgsServerIPAddress] <String>
 [-SafeModeAdministratorPassword <SecureString>] [-LogDirectory <String>] [-DatabasePath <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-HgsServer** cmdlet obtains information about the features, configuration, and state of the local computer, and compares it with the recommended settings to determine whether it can function as a Host Guardian Service (HGS) server node.

The following checks are performed, when applicable: 

- HostGuardianServiceRole installation integrity
- BitLocker is enabled on the operating system drive
- SecureBoot is enabled
- Static IP addresses are configured
- Whether a restart is pending
- Prerequisites for installing a new forest or domain controller in Active Directory, this includes a test report
- Active Directory trust settings
- Validation tests for failover cluster hardware and settings 
- Attestation application pool state
- Key Protection application pool state

For more information about the scenario terms, see [Security and Assurance](http://go.microsoft.com/fwlink/?LinkId=699209).

## EXAMPLES

### Example 1: Test the first HGS node
```
PS C:\> Test-HgsServer -HgsDomainName "Contoso.private"
```

This command tests whether the local computer can be used as the first HGS node.

### Example 2: Test an additional HGS node
```
PS C:\> $Cred = Get-Credential
PS C:\> Test-HgsServer -HgsDomainName "Contoso.private" -HgsServerIPAddress "100.100.100.1" -HgsDomainCredential $Cred
```

This command tests whether the local computer can be used as an additional HGS node.

## PARAMETERS

### -DatabasePath
Specifies a database path.

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

### -HgsDomainCredential
Specifies the Active Directory domain administrator credentials for the primary HGS server.

```yaml
Type: PSCredential
Parameter Sets: AdditionalServer
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HgsDomainName
Specifies the name of the Active Directory domain for the HGS server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HgsServerIPAddress
Specifies the network IP address for the HGS server.

```yaml
Type: String
Parameter Sets: AdditionalServer
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogDirectory
Specifies the output log directory.

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

### -SafeModeAdministratorPassword
Specifies the password for the administrator account when the computer is started in Safe Mode or a variant of Safe Mode, such as Directory Services Restore Mode.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Windows.HostGuardianService.PowerShell.TestReport

## NOTES

## RELATED LINKS

[HGS Server Cmdlets](./hgsserver.md)


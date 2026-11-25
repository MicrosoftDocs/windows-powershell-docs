---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsServer-help.xml
Module Name: HgsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsserver/install-hgsserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-HgsServer
---

# Install-HgsServer

## SYNOPSIS
Installs the Host Guardian Service server.

## SYNTAX

### PrimaryServer_HgsDomain (Default)
```
Install-HgsServer [-HgsDomainName] <String> -SafeModeAdministratorPassword <SecureString> [-Restart]
 [-LogDirectory <String>] [-DatabasePath <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AdditionalServer
```
Install-HgsServer [-HgsDomainName] <String> [-HgsDomainCredential] <PSCredential>
 -SafeModeAdministratorPassword <SecureString> [-Restart] [-LogDirectory <String>] [-DatabasePath <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-HgsServer** cmdlet configures infrastructure components necessary for the Host Guardian Service (HGS) that require reboot.

When this cmdlet is run on the first HGS node, it promotes the node to the primary domain controller for the specified domain.
When this cmdlet is run on an additional HGS node, it promotes the node to a secondary domain controller for the specified domain.

A reboot is necessary for the infrastructure components configured by this cmdlet.

For more information about the scenario terms, see [Security and Assurance](https://go.microsoft.com/fwlink/?LinkId=699209).

## EXAMPLES

### Example 1: Install the HGS server on the current node and prompt for the administrator password
```
PS C:\> Install-HgsServer -HgsDomainName "Contoso.com" -SafeModeAdministratorPassword $SecureStringPassword
```

This command installs the HGS Server on the current node and configures it as the primary server.

### Example 2: Install the HGS server on the current node as a security server and prompt for the administrator password
```
PS C:\> $Credential = Get-Credential
PS C:\> Install-HgsServer -HgsDomainName "Contoso.com" -SafeModeAdministratorPassword $SecureStringPassword -HgsDomainCredential $Credential
```

This command installs the HGS server and uses the current node as a security server.

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

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogDirectory
Specifies the output log directory location.

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

### -Restart
Indicates that a system reboot is initiated after running this command.

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
Specifies the password for the administrator account when the computer is started in Safe Mode or a variant of Safe Mode, such as Directory Services Restore Mode.

```yaml
Type: SecureString
Parameter Sets: (All)
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

## RELATED LINKS

[HGS Server Cmdlets](./hgsserver.md)


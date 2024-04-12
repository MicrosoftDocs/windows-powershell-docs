---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 04/11/2024
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-addomainmode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADDomainMode
---

# Set-ADDomainMode

## SYNOPSIS
Sets the domain mode for an Active Directory domain.

## SYNTAX

```
Set-ADDomainMode [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-DomainMode] <ADDomainMode> [-Identity] <ADDomain> [-PassThru] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-ADDomainMode` cmdlet sets the domain mode for a domain. You specify the domain mode by
setting the **DomainMode** parameter.

The **Identity** parameter specifies the Active Directory domain to modify. You can identify a
domain by its distinguished name, GUID, security identifier (SID), DNS domain name, or NetBIOS
name. You can also set the **Identity** parameter to a domain object variable such as
`$<localADDomainObject>`, or you can pass a domain object through the pipeline to the **Identity**
parameter. For example, you can use the `Get-ADDomain` cmdlet to retrieve a domain object and then
pass the object through the pipeline operator to the `Set-ADDomainMode` cmdlet.

The `Set-ADDomainMode` cmdlet always prompts for permission unless you specify **Confirm:$False**.

## EXAMPLES

### Example 1: Set the domain mode of a specified user to Windows2003Domain

```powershell
Set-ADDomainMode -Identity user01.com -DomainMode Windows2003Domain
```

This command sets the **DomainMode** property of the `user01.com` domain to `Windows2003Domain`.

### Example 2: Set the domain mode of the current user's domain to Windows2003Domain

```powershell
$PDC = Get-ADDomainController -Discover -Service PrimaryDC
Set-ADDomainMode -Identity $PDC.Domain -Server $PDC.HostName[0] -DomainMode Windows2003Domain
```

This example sets the **DomainMode** of the current logged on user's domain to Windows2003Domain.
The set operation targets the PrimaryDC FSMO to apply the update.

## PARAMETERS

### -AuthType

Specifies the authentication method to use. The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the user account credentials to use to perform this task. The default credentials are the
credentials of the currently logged on user unless the cmdlet is run from an Active Directory
module for Windows PowerShell provider drive. If the cmdlet is run from such a provider drive, the
account associated with the drive is the default.

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you can
specify a **PSCredential** object. If you specify a user name for this parameter, the cmdlet
prompts for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the **Credential** parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active
Directory module for Windows PowerShell returns a terminating error.

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

### -DomainMode

Specifies the domain functional level of the first domain in the creation of a new forest.
Supported values for this parameter can be either a valid integer or a corresponding enumerated
string value. For example, to set the domain mode level to Windows Server 2008 R2, you can specify
either a value of **4** or **Windows2008R2Domain**.

The following are the currently supported values:

- Windows Server 2000: **0** or **Windows2000Domain**
- Windows Server 2003 Interim Domain: **1** or **Windows2003InterimDomain**
- Windows Server 2003: **2** or **Windows2003Domain**
- Windows Server 2008: **3** or **Windows2008Domain**
- Windows Server 2008 R2: **4** or **Windows2008R2Domain**
- Windows Server 2012: **5** or **Windows2012Domain**
- Windows Server 2012 R2: **6** or **Windows2012R2Domain**
- Windows Server 2016: **7** or **WinThreshold**
- Windows Server 2025: **10** or **Windows2025Domain**

The domain functional level cannot be lower than the forest functional level, but it can be higher.
The functional level can be increased, and also decreased as long as no feature that requires that
functional level is in use, such as the Active Directory Recycle Bin. The default is automatically
computed and set.

```yaml
Type: ADDomainMode
Parameter Sets: (All)
Aliases:
Accepted values: Windows2000Domain, Windows2003InterimDomain, Windows2003Domain, Windows2008Domain, Windows2008R2Domain, Windows2012Domain, Windows2012R2Domain, Windows2016Domain, Windows2025Domain, UnknownDomain

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies an Active Directory domain object by providing one of the following property values. The
identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the
attribute. All values are for the domainDNS object that represents the domain. The acceptable
values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A DNS domain name
- A NetBIOS domain name

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a
domain object instance.

```yaml
Type: ADDomain
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you are working. By default, this cmdlet does
not generate any output.

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

### -Server

Specifies the Active Directory Domain Services instance to connect to, by providing one of the
following values for a corresponding domain name or directory server. The service may be any of the
following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active
Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order
that they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows
  PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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

Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADDomain

A domain object is received by the **Identity** parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomain

This cmdlet returns the modified domain object when the **PassThru** parameter is specified. By
default, this cmdlet does not generate any output.

## NOTES

- This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
- This cmdlet does not work with an Active Directory snapshot.
- This cmdlet does not work with a read-only domain controller.
- This cmdlet does not work when connected to Global Catalog port.

## RELATED LINKS

[Get-ADDomain](Get-ADDomain.md)

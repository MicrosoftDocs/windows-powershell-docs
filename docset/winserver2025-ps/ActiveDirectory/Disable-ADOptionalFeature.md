---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/disable-adoptionalfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ADOptionalFeature
---

# Disable-ADOptionalFeature

## SYNOPSIS
Disables an Active Directory optional feature.

## SYNTAX

```
Disable-ADOptionalFeature [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADOptionalFeature> [-PassThru]
 [-Scope] <ADOptionalFeatureScope> [-Server <String>] [-Target] <ADEntity>
 [<CommonParameters>]
```

## DESCRIPTION

The `Disable-ADOptionalFeature` disables an Active Directory optional feature that is associated
with a particular domain mode or forest mode.

The **Identity** parameter specifies the Active Directory optional feature that you want to disable.
You can identify an optional feature by its distinguished name, feature GUID, or object GUID. You
can also set the parameter to an optional feature object variable, such as
`$<localOptionalFeatureObject>` or you can pass an optional feature object through the pipeline to
the **Identity** parameter. For example, you can use the `Get-ADOptionalFeature` cmdlet to retrieve
an optional feature object and then pass the object through the pipeline to the
`Disable-ADOptionalFeature` cmdlet.

The **Scope** parameter specifies the scope at which the optional feature is disabled.

The **Target** parameter specifies the domain or forest on which the optional feature is disabled.
You can identify the domain or forest by its fully-qualified domain name (FQDN), NetBIOS name, or
the distinguished name of the domain naming context.

## EXAMPLES

### Example 1: Disable a feature for a NetBIOS target

```powershell
$params = @{
    Identity = 'Feature 1'
    Scope = 'ForestOrConfigurationSet'
    Target = 'fabrikam'
    Server = 'DC1'
}
Disable-ADOptionalFeature @params
```

This command disables the optional feature named `Feature 1` for the forest that has the NetBIOS
name `fabrikam`. This operation should be performed against the domain controller that holds the
domain naming master flexible single master operations (FSMO) role.

### Example 2: Disable a feature by distinguished name

```powershell
$params = @{
    Identity = 'CN=Feature 1,CN=Optional Features,CN=Directory Service,CN=Windows NT,CN=Services,CN=Configuration,DC=fabrikam,DC=com'
    Scope = ForestOrConfigurationSet
    Target = 'fabrikam.com'
    Server = 'DC1'
}
Disable-ADOptionalFeature @params
```

This command disables the optional feature that has the distinguished name
`CN=Feature 1,CN=Optional Features,CN=Directory Service,CN=Windows NT,CN=Services,CN=Configuration,DC=fabrikam,DC=com`,
for the forest named `fabrikam.com`. This operation should be performed against the domain
controller that holds the domain naming master FSMO role.

### Example 3: Disable a feature by GUID

```powershell
$params = @{
    Identity = '54ec6e43-75a8-445b-aa7b-346a1e096659'
    Scope = 'Domain'
    Target = 'DC=fabrikam,DC=com'
    Server = 'DC1'
}
Disable-ADOptionalFeature @params
```

This command disables the optional feature that has the GUID `54ec6e43-75a8-445b-aa7b-346a1e096659`
for the domain with the distinguished name `DC=ntdev,DC=fabrikam,DC=com`. This operation should be
performed against the domain controller that holds the domain naming naming master FSMO role.

### Example 4: Disable a feature for an AD LDS instance

```powershell
$params = @{
    Identity = 'Feature 1'
    Scope = 'ForestOrConfigurationSet'
    Target = 'CN=Configuration,CN={0241853A-6BBF-48AA-8AE0-9C35D0C91B7B}'
    Server = 'server1:50000'
}
Disable-ADOptionalFeature @params
```

This command disables the optional feature `Feature 1` for the Active Directory Lightweight
Directory Services (AD LDS) instance that has the distinguished name
`CN=Configuration,CN={0241853A-6BBF-48AA-8AE0-9C35D0C91B7B}`. This operation should be performed
against the AD LDS instance that holds the domain naming master FSMO role.

## PARAMETERS

### -AuthType

Specifies the authentication method to use.
The acceptable values for this parameter are:

- `Negotiate` or `0`
- `Basic` or `1`

The default authentication method is `Negotiate`.

A Secure Sockets Layer (SSL) connection is required for the `Basic` authentication method.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
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

### -Credential

Specifies the user account credentials to use to perform this task. The default credentials are the
credentials of the currently logged on user unless the cmdlet is run from an Active Directory module
for Windows PowerShell provider drive. If the cmdlet is run from such a provider drive, the account
associated with the drive is the default.

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you can
specify a **PSCredential** object. If you specify a user name for this parameter, the cmdlet prompts
for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the **Credential** parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active
Directory module for Windows PowerShell returns a terminating error.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies an Active Directory optional feature object by providing one of the following values. The
identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the
attribute. The acceptable values for this parameter are:

- FQDN
- Feature GUID (**featureGUID**)
- Object GUID (**objectGUID**)

The cmdlet searches the default naming context or partition to find the object. If two or more
objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an
optional feature object instance.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADOptionalFeature
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you're working. By default, this cmdlet does not
generate any output.

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

### -Scope

Specifies the scope at which the feature is enabled or disabled. The acceptable values for this
parameter are:

- `Domain` or `0`
- `Forest` or `1`

```yaml
Type: Microsoft.ActiveDirectory.Management.ADOptionalFeatureScope
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, ForestOrConfigurationSet, Domain

Required: True
Position: 2
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

The default value for this parameter is determined by one of the following methods in the order that
they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows
  PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target

Specifies the domain or forest in which to modify the optional feature. You can identify the target
domain or forest by providing one of the following values:

- FQDN of the forest or domain
- NetBIOS name of the forest or domain
- Distinguished name of the domain naming context

The following example shows how to set this parameter to a domain naming context.

`-Target "DC=corp,DC=Fabrikam,DC=com"`

```yaml
Type: Microsoft.ActiveDirectory.Management.ADEntity
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

### Microsoft.ActiveDirectory.Management.ADOptionalFeature

An optional feature object is received by the **Identity** parameter.

## OUTPUTS

### None

## NOTES

- This cmdlet doesn't work with an Active Directory snapshot.
- This cmdlet doesn't work with a read-only domain controller.

## RELATED LINKS

[Enable-ADOptionalFeature](./Enable-ADOptionalFeature.md)

[Get-ADOptionalFeature](./Get-ADOptionalFeature.md)

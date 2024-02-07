---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/clear-adclaimtransformlink?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ADClaimTransformLink
---

# Clear-ADClaimTransformLink

## SYNOPSIS
Removes a claims transformation from being applied to one or more cross-forest trust relationships
in Active Directory.

## SYNTAX

```
Clear-ADClaimTransformLink [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADTrust> [-PassThru]
 [-Policy <ADClaimTransformPolicy>] [-Server <String>] [-TrustRole <ADTrustRole>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Clear-ADClaimTransformLink` cmdlet removes a claims transformation from being applied to one or
more cross-forest trust relationships in Active Directory.

## EXAMPLES

### Example 1: Remove a specified policy from a trust relationship

```powershell
Clear-ADClaimTransformLink -Identity 'corp.contoso.com' -Policy DenyAllPolicy
```

This command removes the policy named `DenyAllPolicy` from the `corp.contoso.com` trust.

### Example 2: Remove all policies that are applied to a trusted forest

```powershell
Clear-ADClaimTransformLink -Identity 'corp.contoso.com' -TrustRole Trusted
```

This command removes any policies that are applied to where this forest acts as the trusted forest
in the `corp.contoso.com` trust. Effectively, this cmdlet removes any policies that are applied to
claims flowing out of this forest towards it trust partner.

### Example 3: Remove a claim transformation policy from being applied to the trust relationship

```powershell
$params = @{
    Identity = 'corp.contoso.com'
    Policy = 'DenyAllPolicy'
    TrustRole = 'Trusting'
}
Clear-ADClaimTransformLink @params
```

This command removes DenyAllPolicy that is applied to where this forest acts as the trusted domain
in the `corp.contoso.com` trust. Effectively, this cmdlet removes `DenyAllPolicy` from applying to
claims coming into this from its trust partner.

## PARAMETERS

### -AuthType

Specifies the authentication method to use. The acceptable values for this parameter are:

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

Specifies an Active Directory trust object by providing one of the following values. The identifier
in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (**objectGUID**)

This parameter can also get this object through the pipeline or you can set this parameter to an
object instance.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADTrust
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you're working. By default, this cmdlet doesn't
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

### -Policy

Removes the specified claim transformation policy from being applied to the trust relationship.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy
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

### -TrustRole

Specifies the role of the current forest in the trust relationship specified by the **Identity**
parameter. The allowable values for this parameter are as follows:

- `Trusted`: Specify this value if the current forest is the trusted forest.
- `Trusting`: Specify this value if the current forest is the trusting forest.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADTrustRole
Parameter Sets: (All)
Aliases: 
Accepted values: Trusted, Trusting

Required: False
Position: Named
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

### Microsoft.ActiveDirectory.Management.ADTrust

An account object (**Microsoft.ActiveDirectory.Management.ADTrust**) is received by the **Identity**
parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Set-ADClaimTransformLink](./Set-ADClaimTransformLink.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

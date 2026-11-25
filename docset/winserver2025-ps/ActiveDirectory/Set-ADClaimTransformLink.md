---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adclaimtransformlink?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADClaimTransformLink
---

# Set-ADClaimTransformLink

## SYNOPSIS
Applies a claims transformation to one or more cross-forest trust relationships in Active Directory.

## SYNTAX

```
Set-ADClaimTransformLink [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADTrust> [-PassThru] [-Policy] <ADClaimTransformPolicy> [-Server <String>]
 -TrustRole <ADTrustRole> [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADClaimTransformLink** cmdlet can be used to apply a claims transformation to one or more cross-forest trust relationships in Active Directory.

## EXAMPLES

### Example 1: Set a claims transformation policy to a cross-forest trusted relationship in Active Directory
```
PS C:\> New-ADClaimTransformPolicy -Identity DenyAllPolicy -DenyAll
PS C:\> Set-ADClaimTransformLink "corp.contoso.com" -Policy DenyAllPolicy -TrustRole Trusted
PS C:\> Set-ADClaimTransformLink "corp.contoso.com" -Policy DenyAllPolicy -TrustRole Trusting
```

This command applies the claims transformation policy DenyAllPolicy to the trust corp.contoso.com.
The rule is applied to where this domain acts as both the trusted and trusting domain in the trust.
Effectively, the rule is applied to both claims coming in to this domain from its trust partner, and claims flowing out of this domain towards its trust partner.

Since the specified transformation rule denies all claims to be sent or received, this domain will now deny all claims from being sent to or received from the other domain, the trust partner.

### Example 2: Set a claims transformation policy to a cross-forest trusted relationship in Active Directory
```
PS C:\> New-ADClaimTransformPolicy -Identity AllowAllExceptCompanyAndDepartmentPolicy -AllowAllExcept Company,Department
PS C:\> Get-ADTrust "corp.contoso.com" | Set-ADClaimTransformLink -Policy AllowAllExceptCompanyAndDepartmentPolicy -TrustRole Trusted
```

This command applies the claims transformation policy AllowAllExceptCompanyAndDepartmentPolicy to the trust corp.contoso.com.
The rule is applied to where this domain acts as the trusted domain in the trust.
Effectively, the rule is applied to claims flowing out of this domain towards its trust partner.

Since the specified transformation rule allows all claims to be sent or received except Company and Department, this domain will now allow all claims except the two from being sent to the other domain, the trust partner.

### Example 3: Set a claims transformation policy to a cross-forest trusted relationship in Active Directory
```
PS C:\> New-ADClaimTransformPolicy -Identity HumanResourcesToHrPolicy -Rule 'C1:[Type=="ad://ext/Department:88ce6e1cc00e9524", Value=="Human Resources", ValueType=="string"] => issue(Type=C1.Type, Value="HR", ValueType=C1.ValueType);';
PS C:\> Set-ADClaimTransformLink -Identity "corp.contoso.com" -Policy HumanResourcesToHrPolicy -TrustRole Trusting
```

This command applies the claims transformation policy HumanResourcesToHrPolicy to the trust corp.contoso.com.
The rule is applied to where this domain acts as the trusting domain in the trust.
Effectively, the rule is applied to claims coming in to this domain from its trust partner.

Since the specified transformation rule transforms the value Human Resources into HR in the claim ad://ext/Department:88ce6e1cc00e9524, this domain will now transform the claim value received from the other domain, the trust partner, from Human Resources to HR.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

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

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

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

### -Identity
Specifies an Active Directory group object by providing one of the following values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADTrust
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Policy
Specifies the claims transformation policy to apply to the cross-forest trust relationship.
This parameter does not receive pipeline input.

```yaml
Type: ADClaimTransformPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
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

### -TrustRole
Specifies a trust role, as an enumeration of the link types.
Used to specify which links on the trust relationships that the claims transformation apply to.
The acceptable values for this parameter are:

- Trusted
- Trusting

```yaml
Type: ADTrustRole
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Trusting

Required: True
Position: Named
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADTrust
A trust object is received by the *Identity* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADTrust

## NOTES

## RELATED LINKS

[Clear-ADClaimTransformLink](./Clear-ADClaimTransformLink.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)


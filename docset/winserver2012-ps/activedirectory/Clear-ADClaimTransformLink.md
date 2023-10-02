---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/clear-adclaimtransformlink?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Clear-ADClaimTransformLink

## SYNOPSIS
Removes a claims transformation from being applied to one or more cross-forest trust relationships in Active Directory.

## SYNTAX

```
Clear-ADClaimTransformLink [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADTrust> [-PassThru] [-Policy <ADClaimTransformPolicy>] [-Server <String>]
 [-TrustRole <ADTrustRole>] [<CommonParameters>]
```

## DESCRIPTION
The Clear-ADClaimTransformLink cmdlet removes a claims transformation from being applied to one or more cross-forest trust relationships in Active Directory.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Clear-ADClaimTransformLink "corp.contoso.com" -Policy DenyAllPolicy
```

Description

-----------

Remove the policy named 'DenyAllPolicy' from the 'corp.contoso.com' trust.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Clear-ADClaimTransformLink "corp.contoso.com" -TrustRole Trusted
```

Description

-----------

Remove any policies that are applied to where this forest acts as the trusted forest in the "corp.contoso.com" trust. 
Effectively, this cmdlet removes any policies that are applied to claims flowing out of this forest towards it trust partner.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Clear-ADClaimTransformLink "corp.contoso.com" -Policy DenyAllPolicy -TrustRole Trusting
```

Description

-----------

Remove "DenyAllPolicy" that is applied to where this forest acts as the trusted domain in the "corp.contoso.com" trust.
Effectively, this cmdlet removes "DenyAllPolicy" from applying to claims coming into this from its trust partner.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
Possible values for this parameter include:

Negotiate or 0

Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

The following example shows how to set this parameter to Basic.

-AuthType Basic

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
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
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as "User1" or "Domain01\User01" or you can specify a PSCredential object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then set the Credential parameter to the PSCredential object The following example shows how to create credentials.

$AdminCredentials = Get-Credential "Domain01\User01"

The following shows how to set the Credential parameter to these credentials.

-Credential $AdminCredentials

If the acting credentials do not have directory-level permission to perform the task, Active Directory PowerShell returns a terminating error.

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
Specifies an Active Directory trust object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=fabrikam.com,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set this parameter to a group object instance named "ADTrustInstance".

-Identity $ADTrustInstance

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
Returns the new or modified object.
By default (i.e.
if -PassThru is not specified), this cmdlet does not generate any output.

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
Removes the specified claim transformation policy from being applied to the trust relationship.

```yaml
Type: ADClaimTransformPolicy
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

Fully qualified domain name

Examples: corp.contoso.com

NetBIOS name

Example: CORP

Directory server values:

Fully qualified directory server name

Example: corp-DC12.corp.contoso.com

NetBIOS name

Example: corp-DC12

Fully qualified directory server name and port

Example: corp-DC12.corp.contoso.com:3268

The default value for the Server parameter is determined by one of the following methods in the order that they are listed:

-By using Server value from objects passed through the pipeline.

-By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.

-By using the domain of the computer running Windows PowerShell.

The following example shows how to specify a full qualified domain name as the parameter value.

-Server "corp.contoso.com"

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
Specifies the role of the current forest in the trust relationship specified by the Identity parameter. 
The allowable values for this parameter are as follows:

- Trusted (specify this value if the current forest is the trusted forest)
- Trusting (specify this value if the current forest is the trusting forest)

```yaml
Type: ADTrustRole
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

### Microsoft.ActiveDirectory.Management.ADTrust
An account object (Microsoft.ActiveDirectory.Management.ADTrust) is received by the Identity parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

